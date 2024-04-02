<template>
  <div>
     <div id="header">
        <div class="container">
          <h1>
            {{ title }}
          </h1>
        </div>
     </div>
      <Home />
  </div>
</template>

<script>
  import Home from './components/Home.vue';

  export default{
     name: 'App',
     components:{ Home },
      data() {
        return{
           title: 'inspiring books for you',
        }
      }
  }
</script>

<style>
   #header{
       text-align: center;
       padding-top: 1.5rem;
       padding-bottom: 1.5rem;
       background-color: #000000;
       color: white;
       text-transform: capitalize;
   }
</style>


<!-- 
  This project will give you more knowledge on how to use some vue directives and components

  Vue directives to be use at the cost of this course includes

  1. v-bind directive
  2. v-on directive
  3. v-if, v-else-if, v-show and v-else directives (conditional rendering)
  4. v-for directives (list rendering)
  5. data() function
  6. computed method
  7. methods()
  8. scoped and global styles
  9. local and global registering components

  and some few others.

  => You will learn how to use v-bind on attributes,classes,images,links and booleans
  => you will learn how to use v-if, a conditional rendering directive to manipulate your projects respectively and at thesame know the difference between v-if and v-show directives
  => How to use v-on with @click event to manipulate your html code to make things when there are click 
  => how to use computed method to watch your data properties and make it handle their current state so that when ever the data property is change it reflect in the computed method
  => how to use data to store your properties which can be use in the template through text-interpolation or v-bind directives

  make sure to go through this carefully and tried doing it on your on way and see how good you're 

  GoodLuck!


 -->
