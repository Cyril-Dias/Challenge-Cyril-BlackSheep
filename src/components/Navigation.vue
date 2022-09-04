<template>
  <nav class="navbar navbar-light navbar sticky-top">
    <p>Vous cherchez un cocktail en particulier ? 👉</p>
    <form class="form-inline">
      <input name="s" class="form-control mr-sm-2" type="search" placeholder="Un virgin Mojito ?" aria-label="Search">
      <button class="btn btn-warning my-2 my-sm-0" type="submit">Cherchez</button>
    </form>
  </nav>
</template>

<style>
  .navbar {
    background-color: #800000;
  }
  .navbar p {
    font-size: 1.5rem;
    color: black;
    padding-top: 1rem;
  }
  .btn {
    background: #FF4500;
    border-color: #FF8C00;
  }
</style>