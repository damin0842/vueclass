<template>
  <section id="imgTextType" class="imgText__wrap" :class="attr">
    <h2 class="blind">유용한 사이트 살펴보기</h2>
    <div class="imgText__inner" :class="layout">
      <div class="imgText__txt">
        <span>{{ itTitle.title1 }}</span>
        <h3>{{ itTitle.title2 }}</h3>
        <p>{{ itTitle.title3 }}</p>
        <ul v-for="it in itText" :key="it">
          <li>
            <a :href="it.link">{{ it.name }}</a>
          </li>
        </ul>
      </div>
      <div
        class="imgText__img"
        v-for="id in itDesc"
        :key="id"
        :class="id.class"
      >
        <a :href="id.linkTo" :class="id.class2">{{ id.name }}</a>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: {
    attr: String,
    layout: String,
  },
  data() {
    return {
      itTitle: {
        title1: "이미지 텍스트 유형01",
        title2: "유용한 사이트 살펴보기",
        title3:
          "웹디자이너, 웹 퍼블리셔, 프론트엔드 개발자를 위한 유용한 사이트입니다.",
      },
      itText: [
        {
          name: "튜토리얼 사이트",
          link: "/",
        },
        {
          name: "레퍼런스 사이트",
          link: "/",
        },
        {
          name: "웹폰트 사이트",
          link: "/",
        },
        {
          name: "CSS 사이트",
          link: "/",
        },
        {
          name: "WebGL 사이트",
          link: "/",
        },
        {
          name: "Youtube 사이트",
          link: "/",
        },
      ],
      itDesc: [
        {
          class: "img1",
          name: "레퍼런스 사이트",
          linkTo: "/",
          class2: "",
        },
        {
          class: "img2",
          name: "튜토리얼 사이트",
          linkTo: "/",
          class2: "blue",
        },
      ],
    };
  },
};
</script>

<style>
/* imgTextType */
.imgText__inner {
  display: flex;
  justify-content: space-between;
}

.imgText__inner > div {
  width: 32%;
  height: 500px !important;
}
.imgText__txt {
}
.imgText__txt span {
  font-size: 16px;
  color: #666;
  text-decoration: underline;
  text-underline-position: under;
  margin-bottom: 20px;
}
.imgText__txt h3 {
  font-size: 50px;
  font-weight: bold;
  word-break: keep-all;
  line-height: 1.4;
  margin-bottom: 20px;
  margin-top: 20px;
}
.imgText__txt p {
  font-size: 18px;
  font-weight: 300;
  line-height: 1.5;
  color: #666;
  margin-bottom: 10px;
}
.imgText__txt ul {
  font-size: 18px;
  font-weight: 300;
  line-height: 1.6;
}
.imgText__txt ul li {
  position: relative;
  padding-left: 20px;
}

.imgText__txt ul li a {
  color: #666;
}

.imgText__txt ul li::before {
  content: "";
  width: 5px;
  height: 5px;
  border-radius: 50%;
  position: absolute;
  left: 5px;
  top: 9px;
  background: #666;
}

.imgText__img {
  border-radius: 10px;
  position: relative;
}

.imgText__img a {
  position: absolute;
  left: 30px;
  bottom: 30px;
  background-color: #7c2b39;
  color: #fff;
  font-size: 18px;
  padding: 10px 30px;
  border-radius: 30px;
  display: inline-block;
}
.imgText__img a.blue {
  background-color: #2b387c;
}
.imgText__img.img1 {
  background: url(../../assets/img/imgText_bg01.jpg) no-repeat center / cover;
}
.imgText__img.img2 {
  background: url(../../assets/img/imgText_bg02.jpg) no-repeat center / cover;
}

@media (max-width: 960px) {
  .imgText__inner {
    flex-wrap: wrap;
  }
  .imgText__txt h3 {
    font-size: 40px;
  }
  .imgText__txt p {
    margin-bottom: 60px;
  }
  .imgText__inner > div.imgText__txt {
    width: 100%;
    height: auto;
    text-align: center;
  }
  .imgText__inner > div.imgText__txt ul {
    display: none;
  }
  .imgText__inner > div.imgText__img {
    width: 49%;
  }
}
@media (max-width: 600px) {
  .imgText__txt span {
    font-size: 14px;
    margin-bottom: 10px;
  }
  .imgText__txt h3 {
    font-size: 30px;
  }
  .imgText__txt p {
    margin-bottom: 50px;
    font-size: 16px;
  }
  .imgText__inner > div.imgText__img {
    width: 100%;
    height: 200px;
  }
  .imgText__inner > div.imgText__img.img1 {
    margin-bottom: 20px;
  }
}
</style>