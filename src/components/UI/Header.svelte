<script>
  import { bounceIn } from "svelte/easing";
  export let header;
  export let img;
</script>

<style scoped="scss">
  header {
    height: 100px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.24);
    display: flex;
    background-image: url("https://media.giphy.com/media/10SvWCbt1ytWCc/giphy.gif");
    background-position: center;
    background-size: cover;
    align-content: center;
    align-items: center;
  }
  p {
    color: #333;
    font-family: "Lato", sans-serif;
    font-size: 18px;
    font-weight: bold;
    text-align: center;
    margin-top: 10px;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.46);
    color: #fff;
  }
  .header-title {
    margin: auto;
    display: inline;
  }
  .header-img {
    width: 90px;
    height: 90px;
    vertical-align: middle;
  }
</style>

<header>
  <div class="header-title">
    <p>
      <img src={img} alt="img-portfolio" class="header-img" />
      {header}
    </p>
  </div>
  <div class="" />
</header>
