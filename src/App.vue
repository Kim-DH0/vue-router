<template>
  <div id="nav">
    <ul>
      <li>
        <router-link to="/" class="btn btn-outline-primary">Home</router-link>
      </li>
      <li>
        <router-link to="/join" class="btn btn-outline-primary">Join</router-link>
      </li>
      <li>
        <router-link to="/login" class="btn btn-outline-primary">Login</router-link>
      </li>
      <li>
        <router-link to="/list" class="btn btn-outline-primary">List</router-link>
      </li>
      <li>
        <router-link to="/portfolio" class="btn btn-outline-primary">Portfolio</router-link>
      </li>
    </ul>
  </div>
<!-- <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
  <div class="container-fluid">
    <a class="navbar-brand" href="#"></a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarColor01" aria-controls="navbarColor01" aria-expanded="true" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="navbar-collapse collapse show" id="navbarColor01" style="">
      <ul class="navbar-nav me-auto">
        <li class="nav-item">
          <a class="nav-link active" href="#">Home
            <span class="visually-hidden">(current)</span>
            <router-link to="/Home"></router-link>
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Main</a>
          <router-link to="/Main"></router-link>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Portfolio</a>
          <router-link to="/Portfolio"></router-link>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Join</a>
          <router-link to="/Join"></router-link>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Login<router-link to="/Login"></router-link></a>
          
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">About</a>
          <router-link to="/About"></router-link>
        </li>
      </ul>
      <form class="d-flex">
        <input class="form-control me-sm-2" type="text" placeholder="Search">
        <button class="btn btn-secondary my-2 my-sm-0" type="submit">Search</button>
      </form>
    </div>
  </div>
</nav> -->
<router-view></router-view>
</template>

<style>
@import "./components/bootstrap.css";
  h1 {
    border-radius: 8px;
    background-color: white;
  }
  ul {
    list-style: none;
  }
  li {
    display: inline-block;
    width: 150px;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
