<template lang="ru">
<header class="site-header">
   <div class="main_menu">
    <nav class="navbar navbar-expand-lg navbar-light">
     <div class="container">
      <a class="navbar-brand site-header-logo" href="/">Путевки онлайн</a>
      <a class="btn btn-primary" href="./cart.html">
       Корзина <span class="badge badge-light">4</span>
      </a>
     </div>
    </nav>
   </div>
  </header>
</template>
<script>


export default {
    
}
</script>
<style lang="sass">
.site-header
    z-index: 9999
    transition: background 0.4s, all 0.3s linear
    box-shadow: 0px 10px 17px 3px rgba(221,221,221,0.2)
    background: #fff
    position: fixed !important
    top: 0
    left: 0
    width: 100% !important


.site-header-logo:before
    content: ""
    width: 10px
    height: 10px
    background: #007bff
    display: inline-block
    border-radius: 50%
    margin-right: 7px
    position: relative
    top: -2px


.site-main
    margin-top: 80px


.site-main>.container
    background: #FFF
    padding: 20px



</style>