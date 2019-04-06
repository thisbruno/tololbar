<template>
<v-app>
  <v-toolbar fixed height="73" id="thenabar" class="cyan lighten-3 thenavbar" >
  <a @click="goToXXX" class="d-flex ml-2">
  <img src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-300.png" height="100%" width="65px">
   <v-toolbar-title>Brunow</v-toolbar-title>
  <v-spacer></v-spacer>
   <v-btn flat router to="/skills" class="primary">SKILLs</v-btn> 
    </v-toolbar>
    
</v-app>
</template>

<script>

  export default {
    mounted() {
      this.$nextTick(() => {
          $('.thenavbar').hide()
          // $('.thenavbar').fadeIn('slow')
        // $('#thenavbar').removeAttr('height')

      }),
      $(function(){
        $(window).scroll(function(){
          if($(window).scrollTop() >= 173){
          $('.thenavbar').slideDown(670)
          }
          else{
           $('.thenavbar').slideUp(670)
          }
        })
      }),

      $(function(){
         var prevScrollpos = window.pageYOffset;
        $(window).scroll(function(){
           var currentScrollPos = window.pageYOffset;
       if ( prevScrollpos > currentScrollPos) {
          $('.thenavbar').attr('top','0')
           $('.thenavbar').removeClass('hideNav'); 
         
          }
          else{
             $('.thenavbar').removeAttr('top')
          $('.thenavbar').attr('top','-3409px')
          // console.log("going down");
              $('.thenavbar').addClass('hideNav');                 
          }
           prevScrollpos = currentScrollPos;
        })
      })

    }
  }
</script>

<style scoped>
.thenavbar{
position: sticky;
 top:0px; 
width: 100%;
 transition: top ease-in-out 0.03s;
}

.hideNav{
position:sticky; 
top:-20000px; 
width: 100%;
 transition: top ease-in-out 0.03s;  
}

.SleekNav{
  position:sticky; 
  top: 0px;
  z-index: 2;
}

</style>
