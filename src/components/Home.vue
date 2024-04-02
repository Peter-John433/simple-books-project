<template>
    <div>
        <div class="container cont">
            <div>
                <button @click="toggleBtn">
                    <span v-if="showBooks">hide books</span>
                    <span v-else>show books</span>
                </button>
            </div>
            <div v-if="showBooks">
                <ul>
                    <!-- v-for is use for list rendering, where by the first property represent each item in the array while the second property represent the array object -->
                    <li v-for="book in books" :class="{ fav : book.isFav }" @click="toggleFav(book)">
                        <!-- v-bind is use to bind data property to html dynamically, this take the value from your script and replace it with your html element dynamically -->
                        <!-- <img :src="book.img" :alt="book.title"> -->
                        <img src="../assets/img/note-22.png" alt="">
                        <p>{{ book.title }}</p>
                        <p>{{ book.author }}</p>
                    </li>
                </ul>
            </div>
            <div v-else :class="availableBooks">
                click button above to see all books available
            </div>
        </div>
    </div>
</template>

<script>
  export default{
    name: 'Home',
    data(){
        return{
            books:[
             {
              title: 'you can',
               author: 'GeorgeMatthewAdams',
               img: 'src/assets/img/booknote-1.webp',
               id: 1,
               isFav : true  
             },
             {
               title: 'you can',
               author: 'GeorgeMatthewAdams',
               img: 'src/assets/img/note-2.jpg',
               id: 2,
               isFav: false
             },
             {
              title: 'you can',
               author: 'GeorgeMatthewAdams',
               img: 'src/assets/img/note-3.jpg',
               id: 3,
               isFav: true
             }
           ],
           showBooks: false,
           availableBooks: 'my-books'
        }
    },

    methods:{
        toggleBtn(){
            this.showBooks = !this.showBooks
        },

        toggleFav(book){
            book.isFav = !book.isFav;
        }
    },

    // computed:{
    //     filterBook(){
    //        return this.books.filter( (book) => book.isFav)
    //     }
    // }
  }
</script>

<style scoped>
  .cont{
     padding: 20px;
  }

  .fav{
    background-color: pink;
    color: white;
  }

  button{
     background-color: green;
     width: 100px;
     margin: 1rem auto;
     padding: 4px 0;
     display: block;
     color: #FFFFFF;
     font-weight: bolde;
     text-transform: capitalize;
     border: 2px solid #FFFFFF;
     outline: 2px solid #27ec27;
     cursor: pointer;
     transition: all 500ms ease-in-out;
  }

  button:hover{
    background-color: #27ec27;
    color: #000000;
  }
</style>

 <!-- scoped style is use to style single component, when this a scoped is not apply to your style, the css properties you declared will be visible in all components (apply to all component which have the same element holding those css properties),it's therefore advised to use scoped when using style in your component or file to avoid it been present in all your vue components, furthermore this style property can be overridden in different ways
   ways includes:
   1. by  using a class directly on an element (e.g., .red)
   2 . by combining classes (e.g., .bold.italic)
   3. by overridden the styles in your file component to prevent styles from other components  being applied to yours.
   4. by attaching classes and id to your component elements 
   5. by using global styles to apply to a particular component

   Note: global style is use to make style apply to all vue components present in the vue app, this method can still be overridden using scoped styles method

   ==> when ever you want a particular style to be apply to all your vue components in the same vue application, the best way to go about it is using global scoped to declare all your style properties which we have already done in base.css file and main.css respectively.

   V-FOR DIRECTIVE

   v-for directive is use here to make our codeing easier unlike javascipt that we'll have to use a for loop or forEach() function to render those items, vue make v-for a short process to help our coding life easier, once v-for is use in any element or component, that element or component will repeat itself the number of items in the array or object, and it very easy to go around with, scroll up and you will see where we make use of v-for directive which make our list items repeat X3 (meaning items in the bokks array is 3 so the v-for will have to repeat untill it can no longer repeat again and it stop).
   
   ==> data() in vue is a function that returns and object, once a data() function is declared it must return{} an object for vue to locate all items inside the data, items(properties) in data can be of any type this includes:
   1. string
   2. number
   3. boolean 
   4. array
   5. object
   6 null etc. 

   V-ON DIRECTIVE
  
   2 TYPES OF EVENT HANDLERS IN VUE INCLUDES:

   i. inline handler
   ii. methods handler
   
   * inline handler make you write javascipt function directly in the attributes while  methods handler is just mentioning the method name which was declared in the script,here we make use of method handler, the method handler is use to target where the function is been declared in the script and once the element it's been assigned to is clicked, the function will execute immediately if there's no bug holding back.

   V-IF, V-ELSE AND V-SHOW DIRECTIVES

   these are use for list rendering base on conditions
    
   ==> v-if directive = is use only if the condition is true but if the condition is false the v-else directive is render, the v-else must be declare after v-if directive if not it will not work.
  ==> v-show directive = this is a css property that is use to change the css property of an element i.e it change the display property of an element to none if it been set to FALSE and set it to block if it been set to TRUE, the v-show directive do not destroy the element from Dom rather set the css property to none but the element will be present in the Dom.

  DIFFERENCE BETWEEN V-IF AND V-SHOW 

  1. v-if destroy the property completely from the DOM while v-show hide the property in  the DOM but not remove it using css property 'display: none'.
  2. v-if is use when you want to remove an element completely from DOM while v-show is use when you want to toggle through and elements e.t.c

  DIFFERNCE BETWEEN V-IF AND V-FOR 

  1. v-if must be assign to an element before v-for to avoid breakage  of dom structure.
  2. v-for must not be at the top of v-if in thesame container
  3. v-if as higher value than v-for
-->



