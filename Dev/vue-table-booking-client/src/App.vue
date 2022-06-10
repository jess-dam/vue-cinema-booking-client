<template>
  <div id="app">
    <BookingForm />    
  </div>
</template>

<script>
import BookingForm from './components/BookingForm.vue'

export default {
  name: 'app',
  components: {
    BookingForm
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
  display: flex;
  justify-content: center;
}

h1,h2,h3,h4,label {
  color: #7eebf3;
}

input {
  padding: 20px;
  border-radius: 10px;
  margin: 20px;
  min-width: 300px;
  width: 70%;
}

button {
  background: #7eebf3;
  padding: 10px;
  border-radius: 40px;
  border-color: #7eebf3;
  min-width: 300px;
  margin: 30px;
}

form {
    padding: 20px;
    background: #333333;
    border-radius: 10px;
    min-width: 400px;
    width: 70%;
    height: auto;
    display: grid;
    justify-items: center;
    margin: 30px;
}

textarea {
    min-width: 300px;
    width: 70%;
    margin: 30px;
}
</style>
