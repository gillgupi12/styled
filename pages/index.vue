<script setup lang="ts">
import gsap from "gsap";

onMounted(() => {

  function isInViewport(el: Element) {
          const rect = el.getBoundingClientRect();
          return (
            rect.top >= 0 &&
            rect.left >= 0 &&
            rect.bottom <=
              (window.innerHeight || document.documentElement.clientHeight) &&
            rect.right <=
              (window.innerWidth || document.documentElement.clientWidth)
          );
        }
        const rows = document.querySelectorAll(".row");
        rows.forEach((row) => {
          if (isInViewport(row)) {
            const img = row.querySelector("img");
            if (row.querySelector(".left")) {
              gsap.to(img, {
                clipPath: "polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%)",
              });
            } else {
              gsap.to(img, {
                clipPath: "polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%)",
              });
            }
          }
        });

        (gsap.utils.toArray(".img-container.right img") as HTMLElement[]).forEach(
        (img: HTMLElement) => {
          gsap.to(img, {
            clipPath: "polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%)",
            scrollTrigger: {
              trigger: img,
              start: "top 75%",
              end: "bottom 70%",
              scrub: true,
            },
          });
        });

        (gsap.utils.toArray(".img-container.left img") as HTMLElement[]).forEach(
        (img: HTMLElement) => {
          gsap.to(img, {
            clipPath: "polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%)",
            scrollTrigger: {
              trigger: img,
              start: "top 75%",
              end: "bottom 70%",
              scrub: true,
            },
          });
        });

        (gsap.utils.toArray(".img-container p")as HTMLElement[]).forEach((text) => {
          gsap.from(text, {
            opacity: 0,
            y: 20,
            scrollTrigger: {
              trigger: text,
              start: "top 90%",
              toggleActions: "play none none reverse",
            },
          });
        });

});
</script>

<template>
 <div>
  <div class="header"> </div>

    <div class="container">
      <div class="row" id="row-1">
        <div class="col">
          <div class="canvas img-container right">
            <img src="/0.jpg" alt="" />
            <p>Lunar dreamscape</p>
          </div>
        </div>
        <div class="col"></div>
      </div>
      <div class="row" id="row-2">
        <div class="col"></div>
        <div class="col">
          <div class=" canvas img-container left">
            <img src="/1.jpg" alt="" />
            <p>Futuristic control relic</p>
          </div>
        </div>
      </div>
      <div class="row" id="row-3">
        <div class="col">
          <div class=" canvas img-container right">
            <img src="/2.jpg" alt="" />
            <p>Neo-Tokyo crimson glow</p>
          </div>
        </div>
        <div class="col"></div>
      </div>
      <div class="row" id="row-4">
        <div class="col"></div>
        <div class="col">
          <div class=" canvas img-container left">
            <img src="/3.jpg" alt="" />
            <p>Galactic ocean abyss</p>
          </div>
        </div>
      </div>
      <div class="row" id="row-5">
        <div class="col">
          <div class=" canvas img-container right">
            <img src="/4.jpg" alt="" />
            <p>Hued cosmic dust</p>
          </div>
        </div>
        <div class="col"></div>
      </div>
      <div class="row" id="row-6">
        <div class="col"></div>
        <div class="col">
          <div class="canvas img-container left">
            <img src="/5.jpg" alt="" />
            <p>Silent sentinel</p>
          </div>
        </div>
      </div>
      <div class="row" id="row-7">
        <div class="col">
          <div class=" canvas img-container right">
            <img src="/6.jpg" alt="" />
            <p>Hued cosmic dust</p>
          </div>
        </div>
        <div class="col"></div>
      </div>
      <div class="row" id="row-8">
        <div class="col"></div>
        <div class="col">
          <div class="canvas img-container left">
            <img src="/7.jpg" alt="" />
            <p>Silent sentinel</p>
          </div>
        </div>
      </div>
      <div class="row" id="row-9">
        <div class="col">
          <div class=" canvas img-container right">
            <img src="/8.jpg" alt="" />
            <p>Hued cosmic dust</p>
          </div>
        </div>
        <div class="col"></div>
      </div>
      <div class="row" id="row-10">
        <div class="col"></div>
        <div class="col">
          <div class="canvas img-container left">
            <img src="/9.jpg" alt="" />
            <p>Silent sentinel</p>
          </div>
        </div>
      </div>

      <div class="whitespace"></div>
    </div>

 </div>
</template>
<style >
:root {
  --color-bg: #000000;
  --color-text: #ffffff;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  width: 100%;
  height: 100%;
  background: var(--color-bg);
  font-family: "PP Supply Sans";
}

.header {
  width: 100%;
  height:400px;
  padding: 1em;
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  color: var(--color-text);
}

p {
  font-size: 14px;
  font-weight: 400;
  text-transform: uppercase;
}

img {
  width: 100%;
  height: 100%;
  object-fit: fill;
}

.container {
  width: 100%;
  height: 100%;
}

.row {
  width: 100%;
  display: flex;
}

.col {
  height: 100%;
}

.img-container {
  width: fit-content;
  height: 100%;
}

.img-container.left {
  text-align: right;
}

.img-container p {
  position: relative;
  padding: 5px 0;
  color: var(--color-text);
  opacity: 1;
  transition: opacity 0.3s, transform 0.3s;
}

#row-1 {
  height: 300px;
}

#row-2 {
  height: 500px;
}

#row-3 {
  height: 300px;
}

#row-4 {
  height: 500px;
}

#row-5 {
  height: 300px;
}

#row-6 {
  height: 400px;
}

#row-7 {
  height: 200px;
}

#row-8 {
  height: 600px;
}

#row-9 {
  height: 300px;
}

#row-10 {
  height: 500px;
}

.col:nth-child(1) {
  flex: 3;
  display: flex;
  justify-content: flex-end;
}

.col:nth-child(2) {
  flex: 5;
}


.img-container.right img {
  clip-path: polygon(100% 0, 100% 0, 100% 0, 100% 0);
}

.img-container.left img {
  clip-path: polygon(0 0, 0 0, 0 0, 0 0);
}


.whitespace {
  width: 100%;
  height: 300px;
}
</style>
