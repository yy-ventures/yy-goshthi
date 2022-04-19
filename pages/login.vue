<template>
    <div class="login">
        <div class="login-container">
            <h3>Login to continue registration</h3>
            <form @submit="submit" class="form">
                <div class="userId-container box">
                    <input type="text" v-model="userId" id="user_name" placeholder="User ID">
                    <small>error message</small>
                </div>
                <div class="password-container box">
                    <input type="password" v-model="password" id="password" placeholder="Password">
                    <small>error message</small>
                </div>
                <button id="loginBtn" class="submit-btn" type="submit">Login</button>
            </form>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'

    export default{
        data(){
            return{
                userId: '',
                password: ''
            }
        },
        methods: {  
            submit: async function (e) {
                e.preventDefault();
                // front validation checked
                const success = this.checkInput();
                // Form Data
                const data = new FormData();
                data.set('username', this.userId)
                data.set('password', this.password)
                if(success){
                    const response = await axios.post('http://yyv.yyventures.org/api/login', data)

                    try {
                        if (response.status == 200){
                            this.disableSubmitButton();
                            const headers = {
                            'Content-Type': 'application/json',
                            'Authorization': response.data.data.token
                            }
                            const draftData = await axios.get(`https://yyv.yyventures.org/api/get-app-draft-data?app_id=${this.userId}`, {
                                headers: headers
                            })
                            if(draftData){
                                // localStorage.setItem('draftData', JSON.stringify(draftData.data.data))
                                localStorage.setItem('app_id', draftData.data.data.app_id)                                
                                this.isAppId= true,
                                this.$router.push('/application')
                            }
                        }
                    } catch (err) {
                        console.log(err)
                    }
                }

                // const response = { jwt: 'dgfagsdfgdsfgassdfasd' }

                // console.log(response);

                // localStorage.setItem('jwt', response.jwt);
            },
            checkInput: function(e){
                // e.preventDefault();
                const userId = document.querySelector('#user_name');
                const userPassword = document.querySelector('#password');

                let error = false;
                if(this.userId === ''){
                    this.setErrorFor(userId, 'user ID cannot be empty')
                    error = true;
                } else{
                    this.setSuccessFor(userId)
                }
                if(this.password === ''){
                    this.setErrorFor(userPassword, 'user password cannot be empty')
                    error = true;
                } else{
                    this.setSuccessFor(userPassword)
                }
                return !error;

            },
            disableSubmitButton: function(){
                const loginBtn = document.querySelector('#loginBtn');
                loginBtn.disabled = true;
                loginBtn.style.opacity = '0.4';
                loginBtn.style.cursor = 'wait';
            },
            setErrorFor: function(input, message){
                const formControl = input.parentElement;
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control error';
                small.innerText = message;
            },
            setSuccessFor: function (input) {
                const formControl = input.parentElement;
                const small =  formControl.querySelector('small');

                formControl.className = 'form-control success';
                small.innerText = '';
            },
        }
        
    }
</script>


<style lang="scss" scoped>
    .login{
        padding: 150px 200px;
        .login-container{
            padding: 50px 10px;
            width: 500px;
            background-color: #E0EEF2;
            border-radius: 3px;

            margin-inline: auto;
            h3{
                font-weight: 700;
                color: #363636;
                text-align: center;
            }
            .form{
                padding: 30px 50px;

                display: flex;
                flex-direction: column;

                .submit-btn{
                    border-radius: 3px;
                    border: none;
                }

                input{
                    padding: 10px 8px;
                    font-size: 16px;
                    font-weight: 600;
                    width: 100%;
                    border: 2px solid white;
                }
                .submit-btn{
                    margin-top: 50px;
                    padding: 10px 3px;
                    font-size: 16px;
                    font-weight: 700;
                    cursor: pointer;
                    color: white;
                    background-color: #0b9bbf;

                }
                .box small{
                    visibility: hidden;
                }
                .box{
                    // &:not(:last-child){
                    //     margin-bottom: 1rem;
                    // }
                }
                small{
                    display: block;
                    white-space: nowrap;
                    margin-bottom: 16px;
                }
                .form-control.success input {
                    border-color: #2ecc71;
                }
                .form-control.error input {
                    border-color: #e74c3c;
                }
                .form-control.error small {
                    color: #e74c3c;
                    visibility: visible;
                }

            }
        }
    }
</style>