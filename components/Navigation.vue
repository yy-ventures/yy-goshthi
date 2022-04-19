<template lang="pug">
  nav
    input#toggler(type="checkbox")
    label(for="toggler" )#menu_toggler_label
      #menu_button
        #bar

    nuxt-link.logo(to="/#home")
      img#logo(src="/images/logos/yy_goshthi.png")
    .menu
      a.link.underline(href="/#about") about
      a.link.underline(href="/#impact") impact
      a.link.underline(href="/#benefits") benefits
      a.link.underline(href="/#eligibility") eligibility
      a.link.underline(href="/#alumni") alumni
      a.link.underline(href="/#experts") experts
      a.link(v-on:click='handleVisible = !handleVisible') apply

      .dropdown(v-if='handleVisible')
        //- - var appId = isAppId;
        //- if (!this.isAppId)
        div(v-if='isAppId')
          a.new-form(href='/application')  Application form
          a.login(@click='logout') Logout
          
        div(v-if='!isAppId')
          a.new-form(href='/application') New Application form
          a.login(href='/login') login
          

        //- else

        
</template>

<script>
  export default{
    data(){
      return{
        handleVisible: false,
        handleLoginPopup: false,
        isAppId: false,
        link: 'login',
        isLogin: false
      }
    },
    methods: {
      logout: function(){
        localStorage.removeItem('app_id');
        localStorage.removeItem('draftData')
        this.isAppId = false
        this.link = 'login'
        this.$router.push('/')
      }
    },
    mounted: function() {
      if(localStorage.getItem('app_id') !== null){
        this.isAppId = true
        this.link = 'logout'
      } else{
        this.isAppId = false
        this.link = 'login'
      }
    }
  }
</script>

<style lang="sass">
nav
  background: rgba(white, 0.8)
  // backdrop-filter: blur(5px)

  display: flex
  justify-content: space-between
  align-items: center

  @media (max-width: 601px)
   justify-content: flex-start


  // padding: 5px 30px
  padding: 0 30px

  position: fixed
  width: 100%
  max-width: 1920px
  z-index: 99

  transition: transform 500ms ease-in-out

  input
    display: none

  #toggler:checked
    ~ .menu
      // transform: scale(1)
      transform: translateX(0)
    ~ label #menu_button #bar
      background: none
      margin-top: 7px
      &:before,
      &:after
        top: 0
      &:before
        transform: rotate(45deg)
      &:after
        transform: rotate(-45deg)

  #menu_toggler_label
    @media (min-width: 601px)
      display: none
    #menu_button
      position: absolute

      top: 20px
      right: 10px

      z-index: 99
      cursor: pointer

      padding: 5px 10px
      padding-bottom: 20px

      @media (min-width: 601px)
        display: none

      #bar
        position: relative
        transition: background 500ms
        &, &:after, &:before
          width: 30px
          height: 3px
          background: #333
          border-radius: 50px
        &:after, &:before
          content: ""
          display: block
          position: absolute
          transition: transform 500ms
        &:before
          top: 7px
        &:after
          top: 15px

  #logo
    // position: absolute
    // left: 50%
    // transform: translateX(-50%)
    // z-index: 99
    width: 150px
    @media (max-width: 601px)
      all: unset
      width: 150px


  .menu
    position: absolute
    top: 0
    width: 100vw
    height: 100vh
    transition: transform 500ms
    // transform: scale(0)
    transform: translateX(100%)
    background: #fff

    // display: flex
    // flex-direction: column
    // justify-content: center
    // align-items: center
    padding-top: 100px

    .dropdown
      background: rgba(white, 0.8)
      border: 1px solid $yy-grey

      position: absolute
      right: 0
      top: 60px
      padding: 10px

      a
        text-decoration: none
        font-size: 20px
        font-weight: 500
        width: 100%
        text-align: end
        color: $yy-grey
        &:hover
          color: $yy-blue
      a:not(:last-child)
        margin-bottom: 5px

    .login-btn
        background-color: transparent
        border: none
        font-size: 20px
        font-weight: bold
        color: $yy_blue
        text-transform: capitalize
        cursor: pointer



    @media (min-width: 601px)
      all: unset
      display: flex
      position: relative
      & > * + *
        margin-left: 15px

    a
      display: block !important
      // @media (min-width: 601px)
      //   &:first-of-type
      //     display: none !important


    // display: flex
    // display: none
    //
    // & > * + *
    //   margin-left: 10px
    //
    .nuxt-link-exact-active,
    a:hover
      color: $yy_blue !important

    .link,
    .sub_menu__name
      font-family: 'Graphik'
      font-weight: bold
      color: $yy_grey
      text-transform: capitalize
      padding: 10px
      text-decoration: none
      text-align: center
      cursor: pointer

      font-size: 25px
      @media (min-width: 601px)
        font-size: 18px

    .sub_menu
      &__name:after
        content: ""
        position: absolute
        border: solid $yy_grey
        border-width: 0 3px 3px 0
        transform: rotate(45deg)
        transition: transform 500ms

        padding: 5px
        margin-left: 15px
        margin-top: 10px
        @media (min-width: 601px)
          padding: 3px
          margin-left: 10px
          margin-top: 7px

      .sub_menu__items
        display: none
        @media (min-width: 601px)
          position: absolute
          // margin-top: 5px
          background: rgba(white, 0.9)

      &:hover
        .sub_menu__items
          display: block
        .sub_menu__name:after
          transform: rotate(225deg)
      input:checked
        ~ .sub_menu__items
          display: block
        ~ label .sub_menu__name:after
          transform: rotate(225deg)

    // .sub_menu
    //   &__items
    //     background: rgba(white, 0.9)
    //     position: absolute
    //     z-index: 9
    //     top: 55px
    //     display: none
    //     a
    //       display: block
    //
    //   &__indicators
    //     display: flex
    //     align-items: flex-start
    //
    //     &__icon
    //       border: solid $yy_grey
    //       border-width: 0 3px 3px 0
    //       padding: 3px
    //       transform: rotate(45deg)
    //       -webkit-transform: rotate(45deg)
    //       margin-top: 15px
    // .sub_menu:hover .sub_menu__items
    //   display: block
    // .sub_menu:hover .sub_menu__indicators_icon
    //   transform: rotate(180deg)
</style>
