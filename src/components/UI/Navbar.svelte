<script>
  import Header from "../UI/Header.svelte";
  let segment;

  $: segment = "#project";
</script>

<style>
  nav {
    position: relative;
    width: 100%;
    top: 0;
    left: 0;
    height: 4rem;
    background: #2c3e50;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.26);
  }
  ul {
    margin: 0;
    padding: 0;
    color: #fff;
  }

  /* clearfix */
  ul::after {
    content: "";
    display: block;
    clear: both;
  }

  li {
    display: block;
    float: left;
    margin: 0 0 0 1rem;
  }
  a:hover {
    border-bottom: 2px solid;
    border-bottom-color: #27ae60;
    width: calc(100% - 1em);
  }
  [aria-current] {
    position: relative;
    display: inline-block;
  }

  [aria-current]::after {
    position: absolute;
    content: "";
    width: calc(100% - 1em);
    height: 2px;
    background-color: #27ae60;
    display: block;
    bottom: -1px;
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
  }
</style>

<nav>
  <ul>
    <li>
      <a
        aria-current={segment === undefined ? 'page' : undefined}
        href="#project">
        Project
      </a>
    </li>
    <li>
      <a
        aria-current={segment === '#skills' ? 'page' : undefined}
        href="#skills">
        Skills
      </a>
    </li>
    <li>
      <a
        rel="prefetch"
        aria-current={segment === 'about' ? 'page' : undefined}
        href="about">
        About
      </a>
    </li>
  </ul>
</nav>
<Header header="Portfolio" img="computer.png" />
