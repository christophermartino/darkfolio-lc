<template>
  <div class="layout">
    <div class="line"></div>
    <Header />
      <transition name="fade" appear>
        <main>
    <slot />
  </main>
  </transition>
    <Footer />

  </div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";

export default {
  components: {
    Header,
    Footer
  }
};
</script>

<style lang="scss">
@import url("https://rsms.me/inter/inter.css");
@import url('https://fonts.googleapis.com/css?family=Cormorant+Infant|Kelly+Slab|Old+Standard+TT|UnifrakturMaguntia|Viaoda+Libre&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Yatra+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Eczar:wght@800&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Allan:wght@400;700&family=Anton&family=Bubblegum+Sans&family=Eczar:wght@800&family=Lilita+One&family=Monoton&family=Righteous&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@300;400;600&display=swap');

html {
  font-family: "Inter", sans-serif;
  font-size: 14px;
  font-weight: 500;
  box-sizing: border-box;
}

@supports (font-variation-settings: normal) {
  html {
    font-family: "Inter", sans-serif;
  }
}

*,
*:before,
*:after {
  box-sizing: inherit;
}
body {
  background-color: #131313;
  color: white;
  margin: 0;
  padding: 0;
}
.line {
  width: 100%;
height: 100%;
border-top: 2px solid #222222;
-webkit-transform:
    translateY(40px)
    translateX(1px)
    rotate(-45deg);
position: absolute;
top: -33px;
left: -13px;
z-index: -999;
}
a {
  color: inherit;
  text-decoration: none;
  border-bottom: 1.5px solid transparent;
  padding-bottom: 0.25rem;
  transition: border 0.15s ease;
  &:hover {
    border-bottom: 1.5px solid currentColor;
  }
}
</style>
