<style>
  main {
    display: flex;
    column-gap: 10px;
    margin-top: 100px;
    columns: 6rem auto;
  }
  .card {
    width: 300px;
    color: #e3e3e3;
    cursor: pointer;
    border-radius: 3px;
    background-color: #1f253e;
    box-shadow: 0 1px 2px rgba(25, 25, 25, 0.2);
    margin: 0 auto;
    margin-bottom: 20px;
    padding: 5px;
  }
  hr {
    width: 80%;
    margin: auto;
    color: #333;
  }
  .img-profil {
    width: 100px;
    height: 100px;
  }
</style>

<svelte:head>
  <title>About</title>
</svelte:head>
<main>
  <div class="card">
    <h1>About this site</h1>
    <p>This portfolio is made with Svelte Framework</p>
  </div>
  <hr />
  <div class="card">
    <img src="profil.jpg" alt="profil" class="img-profil" />
  </div>
</main>
