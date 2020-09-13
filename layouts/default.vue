<template>
  <div class='container'>
    <nav class='navbar'>
      <a
        href='/'
        class='nav-link'
      >
        To-Do
      </a>
      <a
        href='/about'
        class='nav-link'
      >
        About
      </a>
    </nav>
    <div class='content'>
      <Nuxt />
    </div>
  </div>
</template>

<style>
:root{
  --background: #303030;
  --theme: #3c6382;
  --theme-accent: #0a3d62;
  --accent: #a0a0a0;
  --contrast: #ffffff;
}

html {
  font-family:
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  color: var(--contrast);
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

body{
  background: var(--background);
}

a{
  color: var(--theme);
}
a::visited{
  color: var(--theme-accent);
}

.container{
  display: flex;
  flex-flow: column;
  flex: 1 1 auto;
  align-items: center;
}

nav{
  display: flex;
  flex: 1 1 auto;
  justify-content: stretch;
  background: var(--theme);
  width: 100%;
}

.nav-link{
  padding: 1em 1.5em;
  background: var(--theme);
  color: var(--contrast);
  text-decoration: none;
  transition: background .1s;
  text-transform: uppercase;
  font-weight: 900;
}

.nav-link:hover, .nav-link:active{
  background: var(--theme-accent);
}

.content{
  margin-top: .5em;
  padding: 0 1em;
  max-width: 720px;
}

img{
  height: 20em;
  max-height: 100vh;
}
@media screen and (max-width: 720px){
  img{
    height: auto;
  }
}
</style>
