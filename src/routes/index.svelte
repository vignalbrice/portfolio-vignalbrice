<script>
  import Header from "../components/UI/Header.svelte";
  import Footer from "../components/UI/Footer.svelte";
  import { fade, blur, fly, slide, scale } from "svelte/transition";
  import { flip } from "svelte/animate";
  import { cubicIn } from "svelte/easing";

  let showDesc = false;
  let whichCard = "";
  let title = "";
  let desc = "";
  let langages = "";
  let link = "";
  let website = "";
  const onChangeData = data => {
    whichCard = data;
    showDesc = true;

    if (whichCard === "todo") {
      title = "Todo Svelte App";
      desc = "Todo app based on framework svelte, with check or add methods";
      langages = ["Svelte", "HTML", "CSS", "JavaScript"];
      link = "https://github.com/vignalbrice/svelte-todo";
      website = "http://svelte-todo.s3-website.us-east-2.amazonaws.com/";
    }
    if (whichCard === "meetups") {
      title = "Meetups Svelte App";
      desc = "Metup web application to get an meetup by id and see details";
      langages = ["Svelte", "HTML", "CSS", "JavaScript", "Firebase"];
      link = "https://github.com/vignalbrice/svelte-sapper";
      website = "http://sapper-app.s3-website.us-east-2.amazonaws.com/";
    }
    if (whichCard === "newspaper") {
      title = "NewsPaper Svelte App";
      desc = "News App integrated sveltejs framework and work with newsapi.com";
      langages = ["Svelte", "HTML", "CSS", "JavaScript", "API"];
      link = "https://github.com/vignalbrice/svelte-sapper";
    }
  };
</script>

<style>
  main {
    width: 1024px;
    margin: auto;
  }
  .grid {
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
    border-bottom-left-radius: 15px;
    border-bottom-right-radius: 15px;
  }
  .content {
    align-content: center;
    align-items: center;
    text-align: center;
  }
  .card-media {
    width: 100%;
    object-fit: cover;
    background: #333;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
  }
  .date,
  .title,
  .type,
  .tags {
    margin: 10px 10px 10px 10px;
  }
  .tags {
    margin: 0;
    overflow: hidden;
    list-style: none;
    padding: 0;
  }
  @media (min-width: 768px) {
    .card {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  @media screen and (min-width: 646px) {
    .grid {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  @media screen and (min-width: 364px) {
    .grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  h4.date {
    font-size: 0.75em;
    color: #858aa0;
    font-family: "Lato", sans-serif;
  }
  h2.title {
    font-size: 1em;
    font-family: "Lato", sans-serif;
    font-weight: 900;
  }
  .type {
    margin: 15px 10px;
    font-family: "Lato", sans-serif;
    color: #858aa0;
  }
  ul {
    margin: 0;
    overflow: hidden;
    list-style: none;
    padding: 0;
  }
  li {
    margin: 2px 2px;
  }
  a {
    padding: 4px 4px 3px 4px;
    font-size: 0.7em;
    font-family: "Roboto", sans-serif;
    background-color: #0a1028;
    border-radius: 5px;
    text-decoration: none;
    -webkit-transition: color 0.2s;
  }
  .svelte {
    color: #ff3e00;
  }
  .html {
    color: #f16625;
  }
  .css {
    color: #264ee4;
  }
  .javascript {
    color: #f7df1e;
  }
  .firebase {
    color: #ffca28;
  }
  .card-description {
    margin: 1em 0em;
    padding: 1em;
    background-color: #1f253e;
    border-radius: 15px;
  }
  .card-description h3 {
    color: #e3e3e3;
    font-weight: 700;
    margin: 10px 0 10px 0;
  }
  .card-description p {
    color: #858aa0;
    margin: 20px 0 20px 0;
  }
  .card-description .link {
    text-align: center;
    margin: 10px;
    color: #e3e3e3;
    font-size: 50px;
  }
  .card-description ul {
    display: inline-flex;
  }
  .card-skills {
    margin-top: 50px;
  }
  .about-image {
    background-position: 50% 30%;
    background-size: cover;
    height: 600px;
    background-image: url("../../responsive.svg");
    background-color: #34495e;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
  }
  .content-image {
    display: flex;
    flex-direction: column;
    color: #fff;
  }
  .content-image h1,
  h3 {
    font-family: sans-serif;
    margin: 10px 0 0 20px;
    text-shadow: 0px 2px 4px rgba(0, 0, 0, 0.46);
  }
  .describe {
    background-color: #858aa0;
    padding: 4px;
  }

  .describe p {
    line-height: 1.75;
    text-align: center;
    color: #fff;
  }
  .content-skill {
    background-color: #1f253e;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-around;
    border-radius: 0 0 15px 15px;
  }
  .skill-lang,
  .skill-learn,
  .skill-lib {
    display: flex;
    align-items: center;
    margin: 20px;
    max-width: 300px;
  }
  .flex-container {
    padding: 0;
    margin: 0;
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
  }
  .flex-item {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
  }
  .flex-item p {
    padding-right: 15px;
    font-weight: 600px;
  }
  .tag-html {
    color: #ff8c4e;
    font-weight: 600;
  }
  .tag-css {
    color: #3899d4;
    font-weight: 600;
  }
  .tag-js {
    color: #ffde56;
    font-weight: 600;
  }
  .progress-bar progress {
    -webkit-appearance: none;
    padding: 3px;
    background: #0a1028;
    border-radius: 15px;
    border-style: none;
    box-shadow: inset 0px 1px 1px rgba(0, 0, 0, 0.5);
  }
  progress::-moz-progress-bar {
    border-radius: 15px !important;
    background: #0a1028;
  }
  progress::-webkit-progress-bar {
    border-radius: 15px !important;
    background: #0a1028;
  }
  .html::-webkit-progress-value {
    background: #ff8c4e;
    border-radius: 15px;
  }
  .css::-webkit-progress-value {
    background: #3899d4;
    border-radius: 15px;
  }
  .js::-webkit-progress-value {
    background: #ffde56;
    border-radius: 15px;
  }
  .skill-learn ul {
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: row;
    list-style-type: none;
  }
  .skill-learn ul > li {
    margin: 10px;
  }
  .learn-icon {
    display: flex;
    flex-direction: row;
    justify-content: center;
  }
  .learn-icon a {
    color: inherit;
    text-decoration: none;
    text-align: center;
    background: none !important;
  }
  .learn-icon a > img {
    width: 60px;
  }
  .svelte-img {
    width: 35px !important
    ;
  }
  .vue-img {
    width: 40px !important
    ;
  }
  .flex-container2 {
    padding: 0;
    margin: 0;
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
    justify-content: center;
  }
  .about-tab {
    padding: 3px 10px;
    font-family: "Roboto", sans-serif;
    background-color: #0a1028;
    text-decoration: none;
    border-radius: 15px;
    -webkit-transition: color 0.2s;
    font-weight: 600;
  }
  .about-tab i {
    margin-right: 5px;
  }
  .about-tab a {
    text-decoration: none;
  }
  .bootstrap {
    color: #7952b3;
  }
  .sql {
    color: #f29221;
  }
  .mongodb {
    color: #13aa52;
  }
  .nodejs {
    color: #43853d;
  }
  .describe p {
    font-weight: 600;
    font-size: 18px;
  }
  #contact {
    align-content: center;
    align-items: center;
    text-align: center;
    margin-top: 3rem;
    margin-bottom: 3rem;
  }
  a.email {
    font-size: 20px;
    background: none;
    text-decoration: none;
    color: #fff;
  }
  .socials {
    display: inline;
  }
  .socials a {
    color: inherit;
    text-decoration: none;
    margin: 10px;
    background: none !important;
  }
  .gitIcon {
    color: #505c91;
  }
  .contactIcon {
    color: #27ae60;
  }
  .linkedinIcon {
    color: #2980b9;
  }
</style>

<svelte:head>
  <title>Portfolio Vignal Brice</title>
</svelte:head>
<main id="project">
  <div class="grid">
    <div
      class="card"
      on:click={() => {
        onChangeData('todo');
      }}>
      <img src="todo.png" alt="todo" class="card-media" />
      <div class="content">
        <h4 class="date">2020</h4>
        <h2 class="title">Todo Svelte</h2>
        <div class="type">One Page</div>
        <div class="tags">
          <ul>
            <li>
              <a href="https://svelte.dev/" target="_blank" class="svelte">
                Svelte
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div class="card" on:click={() => onChangeData('meetups')}>
      <img src="meetups.png" alt="todo" class="card-media" />
      <div class="content">
        <h4 class="date">2020</h4>
        <h2 class="title">Meetup Svelte</h2>
        <div class="type">One Page</div>
        <div class="tags">
          <ul>
            <li>
              <a href="https://svelte.dev/" target="_blank" class="svelte">
                Svelte
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div class="card" on:click={() => onChangeData('newspaper')}>
      <img src="news.png" alt="todo" class="card-media" />
      <div class="content">
        <h4 class="date">2020</h4>
        <h2 class="title">NewsPaper Svelte</h2>
        <div class="type">One Page</div>
        <div class="tags">
          <ul>
            <li>
              <a href="https://svelte.dev/" target="_blank" class="svelte">
                Svelte
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
  {#if showDesc}
    <div
      class="card-description"
      transition:fly={{ easing: cubicIn, x: 200, y: 0 }}>
      <h3>{title}</h3>
      <p>{desc}</p>
      <div class="tags">
        <ul>
          {#each langages as item}
            <li>
              <a href={`#${item}`} class={item.toLowerCase()}>{item}</a>
            </li>
          {/each}
        </ul>
      </div>
      <div class="link">
        <a href={link} target="_blank">
          <i class="fab fa-github" />
        </a>
        <a href={website ? website : '#'} target="_blank">
          <i class="fas fa-arrow-alt-circle-right" />
        </a>
      </div>
    </div>
  {/if}
</main>
<br />
<Header header={'Skills'} img={'pngwave.png'} />
<main id="skills">
  <div class="card-skills">
    <div class="about-image">
      <div class="content-image">
        <h1>Brice Vignal</h1>
        <h3>Développeur Front Web & Mobile - Paris</h3>
      </div>
    </div>
    <div class="describe">
      <p>
        Actuellement en poste en tant que Développeur Front-End chez InfoPro
        Digital en collaboration avec l'Ecole Multimédia
      </p>
    </div>
    <div class="content-skill">
      <div class="skill-lang">
        <div class="flex-container">
          <div class="flex-item">
            <p class="tag-html">HTML</p>
            <div class="progress-bar">
              <progress min="0" max="100" value="90" class="html" />
            </div>
          </div>
          <div class="flex-item">
            <p class="tag-css">CSS</p>
            <div class="progress-bar">
              <progress min="0" max="100" value="90" class="css" />
            </div>
          </div>
          <div class="flex-item">
            <p class="tag-js">JavaScript</p>
            <div class="progress-bar">
              <progress min="0" max="100" value="80" class="js" />
            </div>
          </div>
        </div>
      </div>
      <div class="skill-learn">
        <ul>
          <li>
            <div class="learn-icon">
              <a href="https://svelte.dev/">
                <img
                  src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Svelte_Logo.svg/langfr-220px-Svelte_Logo.svg.png"
                  class="svelte-img"
                  alt="svelte" />
              </a>
            </div>
          </li>
          <li>
            <div class="learn-icon">
              <a href="https://fr.reactjs.org/">
                <img
                  src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/langfr-220px-React-icon.svg.png"
                  alt="react" />
              </a>
            </div>
          </li>
          <li>
            <div class="learn-icon">
              <a href="https://vuejs.org/">
                <img
                  class="vue-img"
                  src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/langfr-220px-Vue.js_Logo_2.svg.png"
                  alt="vue" />
              </a>
            </div>
          </li>
        </ul>
      </div>
      <div class="skill-lib">
        <ul class="flex-container2">
          <li class="flex-item">
            <div class="about-tab bootstrap">
              <i class="fas fa-mobile-alt" />
              <a
                target="_blank"
                href="https://getbootstrap.com/"
                class="tag-bootstrap">
                Bootstrap
              </a>
            </div>
          </li>
          <li class="flex-item">
            <div class="about-tab sql">
              <i class="fas fa-database" />
              <a target="_blank" href="https://www.mysql.com/" class="tag-sql">
                MySQL
              </a>
            </div>
          </li>
          <li class="flex-item">
            <div class="about-tab mongodb">
              <i class="fas fa-leaf" />
              <a
                target="_blank"
                href="https://www.mongodb.com/"
                class="tag-mongodb">
                MongoDB
              </a>
            </div>
          </li>
          <li class="flex-item">
            <div class="about-tab nodejs">
              <i class="fab fa-node-js" />
              <a
                target="_blank"
                href="https://nodejs.org/en/"
                class="tag-nodejs">
                NodeJS
              </a>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</main>
<br />

<Header
  header={'Contact'}
  img={'https://cdn.onlinewebfonts.com/svg/img_162044.png'} />
<main id="contact">
  <a href="mailto:vignal.brice@gmail.com" class="email">
    vignal.brice@gmail.com
  </a>
  <div class="socials">
    <a href="https://github.com/vignalbrice" target="_blank" class="">
      <i class="fab fa-github-alt fa-3x gitIcon" />
    </a>
    <a href="#V" target="_blank" class="">
      <i class="far fa-address-card fa-3x contactIcon" />
    </a>
    <a
      href="https://www.linkedin.com/in/brice-vignal-302307146/"
      target="_blank"
      class="">
      <i class="fab fa-linkedin fa-3x linkedinIcon" />
    </a>
  </div>
</main>
<Footer />
