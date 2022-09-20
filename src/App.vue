<template>
<div>
    <div>{{ greet }}{{ name }}</div>
    <!-- binding to text -->
    <div v-text="name"></div>
    
    <!-- binding to html -->
    <div v-html="win"></div>
    <div v-html="ans"></div>
    
    <!-- binding to Attributes -->
    <h2 v-bind:id="headingId">heading</h2>
    <button v-bind:disabled="isDisabled">Bind</button>
    
    <!-- binding to class -->
    <h2 class="underline">Underline text</h2>
    <h2 class="underline" v-bind:class="status">Status</h2>
    <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movies</h2>
    <!-- using Ternary Operator on binding to class 
        Ternary-Operator-Syntax: condition ? <expression if true> : <expression if false>-->
    <h2 v-bind:class="isSoldout ? 'sold-out':'new'">Soldout? Movies</h2>
    <h2 v-bind:class="['new','promoted']">Newly promoted movies</h2>
    <h2 v-bind:class="[isPromoted && 'promoted',isSoldout ? 'sold-out':'new']">Array conditional movies</h2>
    <h2 v-bind:class="{
      promoted:isPromoted,
      new:isSoldout,
      'sold-out':!isSoldout
    }">object conditional movies</h2>
    
    
    <!-- style bind:inline syntax, object syntax, array syntax  -->
    <!-- inline syntax -->
    <h2 v-bind:style="{
      color:highlightColor,
      'font-size':headerSize + 'px',
      padding:'5px'
    }">Inline Style</h2>
    <!-- object syntax -->
    <h2 v-bind:style="headerStyleObject">Object Style </h2>
    <!-- array syntax -->
    <div v-bind:style="[baseStyleObject,successStyle]">Array style</div>
</div>

</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      greet: "Hello",
      name: "Tohin",

      // binding to html
      win: "<b>vue.js kmn sikhtecho?</b>",
      ans: `<a href="#" onclick="alert('Joss !!!')">Alhamdulillah!<a/>`,

      // binding to attribute
      headingId: 'heading',
      isDisabled: false, //boolean attribute

      // binding to class
      status: 'danger',
      isPromoted: true,
      isSoldout: true,

      // nline style bind
      highlightColor: 'orange',
      headerSize: 50,
      headerStyleObject: {
        color: 'red',
        fontSize: "30px",
        padding: '20px',
      },
      baseStyleObject: {
        fontSize: '50px',
        padding: '10px',
      },
      successStyle: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green'
      }

    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

/* class binding : defined "underline" class  */
.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: blueviolet;
}

.sold-out {
  color: red;
}
</style>
