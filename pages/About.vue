<template>
  <div class="container animate__animated animate__fadeIn">
    <div class="row">
      <div class="col-md-6">
        <div class="about">
          <h1 class="line-after">Sobre mim</h1>
          <h4 class="mt-4">olá 👋</h4>
          <p>
           Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam aut, quas nesciunt facere cumque quod molestiae inventore doloremque adipisci voluptas est, possimus, reprehenderit recusandae quis aliquam unde velit repellendus nemo.
          </p>
          <p>
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Expedita odio eveniet odit at et qui, repudiandae vero, ratione, debitis alias natus iure voluptate ducimus modi inventore molestiae earum ad. Dolorum?
          </p>
          <h4 class="mt-5">Linguagens</h4>
          <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Rem at mollitia commodi esse suscipit? Ducimus repellat quae esse magnam, natus exercitationem corporis vitae! Ipsam, rerum magnam temporibus nesciunt voluptas voluptatum?</p>
          <div class="row animate__animated animate__fadeInUp">
            <div class="col">
              
            </div>
            <div class="col">
              <ul style="list-style-type: circle">
                
              </ul>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6">
        <img
          src="https://www.wareline.com.br/wp-content/uploads/2018/11/2018-11-05-Post3.png"
          alt=""
          class="abt-img"
        />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      startYear: 2021,
      currYear: new Date().getFullYear(),
      stacks: [
        {
          language: "HTML",
          experience: "3+ Years",
          variant: "secondary",
          breif: "lorem...",
        },
        {
          language: "CSS",
          experience: "3+ Years",
          variant: "primary",
          breif: "lorem...",
        },
        {
          language: "Javascript",
          experience: "2+ Years",
          variant: "warning",
          breif: "lorem...",
        },
        {
          language: "VUE.JS",
          experience: "2+ Years",
          variant: "success",
          breif: "lorem...",
        },
        {
          language: "Node.js",
          experience: "2+ Years",
          variant: "dark",
          breif: "lorem...",
        },
      ],
    };
  },
  head: {
    title: "Sobre Matheus",
    meta: [
      {
        hid: "description",
        name: "description",
        // currYear - startYear
        content: `A Lightweight and Stable Discord Music Bot For Your Daily Production.`,
      },
    ],
  },
};
</script>
<style scoped>
.container {
  margin-top: 140px;
  text-align: left;
}
.line-after {
  overflow: hidden;
}
.line-after::after {
  content: "";
  display: inline-block;
  height: 0.5em;
  vertical-align: bottom;
  width: 100%;
  margin-right: -100%;
  margin-left: 10px;
  border-top: 2px solid rgb(211, 46, 46);
}
.abt-img {
  width: inherit;
  height: inherit;
  border-radius: 5px;
}
/* .abt-img:hover {
  animation: swing;
  animation-duration: 2s;
} */
</style>
