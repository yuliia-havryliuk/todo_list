<template>
  <div id="app">
    <h1>TODOLIZER</h1>
    <hr>
    <router-view />
  </div>
</template>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: #ffe5e6;
  border: #2c3e50 3px solid;
  display: block;
  width: 800px;
  height:auto;
  margin-left: auto;
  margin-right: auto;
  padding-bottom: 10px;
}
  body{
    background-color: #2c3e50;
  }
</style>
