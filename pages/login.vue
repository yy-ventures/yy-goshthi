<template>
    <div class="login">
        <div class="login-container">
            <h3>Login to continue registration</h3>
            <form @submit="submit" class="form">
                <input type="text" v-model="userId" id="user_name" placeholder="User ID">
                <input type="password" v-model="password" id="password" placeholder="Password">
                <button class="submit-btn" type="submit">Login</button>
            </form>
        </div>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                userId: '',
                password: ''
            }
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

                input, .submit-btn{
                    border-radius: 3px;
                    border: none;
                }

                input{
                    padding: 10px 8px;
                    font-size: 16px;
                    font-weight: 600;
                }
                input:not(:last-child){
                    margin-bottom: 20px;
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
            }
        }
    }
</style>