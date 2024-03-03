<script>
</script>

<svg style="display:none;">
  <defs>
    <g id="home">
      <path fill="#90A4AE" d="M42,48H6c-3.3,0-6-2.7-6-6V6c0-3.3,2.7-6,6-6h36c3.3,0,6,2.7,6,6v36C48,45.3,45.3,48,42,48z"/>
      <path fill="#212121" d="M20.8,35.5v-9.6h6.4v9.6h8V22.7H40L24,8.3L8,22.7h4.8v12.8H20.8z"/>
    </g>

    <g id="settings">
      <path fill="#90A4AE" d="M24 13.616v-3.232c-1.651-.587-2.694-.752-3.219-2.019v-.001c-.527-1.271.1-2.134.847-3.707l-2.285-2.285c-1.561.742-2.433 1.375-3.707.847h-.001c-1.269-.526-1.435-1.576-2.019-3.219h-3.232c-.582 1.635-.749 2.692-2.019 3.219h-.001c-1.271.528-2.132-.098-3.707-.847l-2.285 2.285c.745 1.568 1.375 2.434.847 3.707-.527 1.271-1.584 1.438-3.219 2.02v3.232c1.632.58 2.692.749 3.219 2.019.53 1.282-.114 2.166-.847 3.707l2.285 2.286c1.562-.743 2.434-1.375 3.707-.847h.001c1.27.526 1.436 1.579 2.019 3.219h3.232c.582-1.636.75-2.69 2.027-3.222h.001c1.262-.524 2.12.101 3.698.851l2.285-2.286c-.744-1.563-1.375-2.433-.848-3.706.527-1.271 1.588-1.44 3.221-2.021zm-12 2.384c-2.209 0-4-1.791-4-4s1.791-4 4-4 4 1.791 4 4-1.791 4-4 4z"/>
    </g>

    <g id="search">
      <path fill="#90A4AE" d="M22.9,20.1h-1.5l-0.5-0.5c1.8-2.1,2.9-4.8,2.9-7.7C23.8,5.3,18.5,0,11.9,0S0,5.3,0,11.9s5.3,11.9,11.9,11.9
        c3,0,5.7-1.1,7.7-2.9l0.5,0.5v1.4l9.1,9.1l2.7-2.7L22.9,20.1z M11.9,20.1c-4.5,0-8.2-3.7-8.2-8.2s3.7-8.2,8.2-8.2s8.2,3.7,8.2,8.2
        S16.4,20.1,11.9,20.1z"/>
    </g>

    <g id="map">
      <path fill="#90A4AE" d="M16,14.2c-1,0-1.8,0.8-1.8,1.8s0.8,1.8,1.8,1.8c1,0,1.8-0.8,1.8-1.8S17,14.2,16,14.2z M16,0
        C7.2,0,0,7.2,0,16c0,8.8,7.2,16,16,16s16-7.2,16-16C32,7.2,24.8,0,16,0z M19.5,19.5L6.4,25.6l6.1-13.1l13.1-6.1L19.5,19.5z"/>
    </g>

    <g id="planner">
      <path fill="#90A4AE" d="M28.4,3.6h-1.8V0h-3.6v3.6H8.9V0H5.3v3.6H3.6C1.6,3.6,0,5.1,0,7.1L0,32c0,2,1.6,3.6,3.6,3.6h24.9c2,0,3.6-1.6,3.6-3.6V7.1C32,5.1,30.4,3.6,28.4,3.6z M28.4,32H3.6V12.4h24.9V32z M7.1,16H16v8.9H7.1V16z"/>
    </g>

  </defs>
</svg>

<nav class="nav__cont">
  <ul class="nav">
    <li class="nav__items ">
      <a class="nav__svg" href="/" role="button">
        <svg  xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 48">
          <use xlink:href="#home"></use></svg>
          Home</a>
    </li>
    
      
    <li class="nav__items ">
      <a class="nav__svg" href="/map" role="button">
        <svg  xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32">
          <use xlink:href="#map"></use></svg>
          Map</a>
    </li>
      
    <li class="nav__items ">
      <a class="nav__svg" href="/settings" role="button">
        <svg  xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
          <use xlink:href="#settings"></use></svg>
        Settings</a>
    </li>
        
  </ul>
</nav>

<style>
  .nav__cont {
    top:0;
    height: 100vh;
    z-index: 100;
    background-color: #202020;
    overflow:hidden;
    transition:width .3s ease;
    cursor:pointer;
    box-shadow:4px 7px 10px rgba(0,0,0,.4);
  }

  .nav {
    list-style-type: none;
    color:white;

    &:first-child {
        padding-top:1.5rem;
    }
  }

  .nav__items {
    padding-bottom:4rem;
    font-family: 'roboto';
  }

  a {
    position: relative;
    display:block;
    top:-25px;
    padding-right:5px;
    transition:all .3s ease;
    margin-right:5px;
    text-decoration: none;
    color:white;
    font-family: 'roboto';
    font-weight: 100;
    font-size: 1em;
    align-items: center;
  }

  &:after {
    content:'';
    width: 100%;
    height: 100%;
    position: absolute;
    top:0;
    left:0;
    border-radius:2px;
    background:radial-gradient(circle at 94.02% 88.03%, #54a4ff, transparent 100%);
    opacity:0;
    transition:all .5s ease;
    z-index: -10;
  }

  &:hover a:after {
      opacity:1;
  }

  .nav__svg {
      width:26px;
      height:26px;
      position: relative;
      left:-25px;
      cursor:pointer;
      @media screen and (min-width:600px) {
          width:32px;
          height:32px;
          left:-15px;
      }
  }
</style>
