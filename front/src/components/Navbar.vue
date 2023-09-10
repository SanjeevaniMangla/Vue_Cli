<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <router-link class="navbar-brand text-style" to="/" style='margin-right:1140px'>
          Flask and Vue3
      </router-link>
  
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <router-link class="btn btn-primary" aria-current="page" to="/" style='margin-right:16px'>Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="btn btn-success" to="/create">Create</router-link>
          </li>
        </ul>
      </div>
    </div>
     </nav>
  </template>
  
  <script>
  export default {
  
  }
  </script>
  
  <style>
  .text-style{
      font-size: 30px !important;
      font-family: fantasy !important;
      color: brown !important;
  }
  
  </style>