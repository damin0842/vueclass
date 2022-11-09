<template>
  <section id="cardType" class="card__wrap" :class="attr">
    <h2>{{ cardTitle.title }}</h2>
    <p>{{ cardTitle.desc }}</p>
    <div class="card__inner" :class="layout">
      <article class="card" v-for="ct in cardText" v-bind:key="ct">
        <figure class="card__header">
          <img :src="ct.imgSrc" alt="{{ct.cardTitle}}" />
        </figure>
        <div class="card__body">
          <h3 class="tit">{{ ct.cardTitle }}</h3>
          <p class="desc">
            {{ ct.cardDesc }}
          </p>
          <a :href="ct.btnLink" class="btn">
            {{ ct.linkText }}
            <span aria-hidden="true">
              <svg
                width="101"
                height="8"
                viewBox="0 0 101 8"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M100.354 4.35355C100.549 4.15829 100.549 3.84171 100.354 3.64645L97.1716 0.464466C96.9763 0.269204 96.6597 0.269204 96.4645 0.464466C96.2692 0.659728 96.2692 0.976311 96.4645 1.17157L99.2929 4L96.4645 6.82843C96.2692 7.02369 96.2692 7.34027 96.4645 7.53553C96.6597 7.7308 96.9763 7.7308 97.1716 7.53553L100.354 4.35355ZM0 4.5H100V3.5H0V4.5Z"
                  fill="black"
                />
              </svg>
            </span>
          </a>
        </div>
      </article>
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
      cardTitle: {
        title: "어린이 식물 관찰 교실🌲",
        desc: "다육식물정원, 아열대정원, 무늬정원, 사막정원 등 체험하고 관찰",
      },
      cardText: [
        {
          imgSrc: "../../assets/img/card_bg01.jpg",
          cardTitle: "식물클리닉 교실",
          cardDesc: `가정에서 식물 키우기와 분갈이, 병충해 관리 등의 어려움을 해소하고
            식물의 건강한 관리를 위한 유익한 전문지식을 배우는 수업입니다.`,
          btnLink: "/",
          linkText: "더 자세히 보기",
        },
        {
          imgSrc: "../../assets/img/card_bg02.jpg",
          cardTitle: "자생식물 사진교실",
          cardDesc: `식물과 다양한 생물을 사진으로 표현하는 강좌로 사진에 대한 이해와
            촬영 기술을 학습을 바탕으로 전시원 현장을 돌면서 실습하는
            수업입니다.`,
          btnLink: "/",
          linkText: "더 자세히 보기",
        },
        {
          imgSrc: "../../assets/img/card_bg03.jpg",
          cardTitle: "식물세밀화 교실",
          cardDesc: `식물세밀화란 식물이 가진 특징을 정확히 관찰하고 묘사하여 기록함과
            동시에 아름다운 형태로 구성하는 과정에서 창작의 의미가 부여되는 예술
            입니다.`,
          btnLink: "/",
          linkText: "더 자세히 보기",
        },
      ],
    };
  },
};
</script>
<style>
/* cartType */
.card__inner {
  display: flex;
  justify-content: space-between;
}
.card {
  width: 32%;
  background: #f5f5f5;
}
.card__body {
  padding: 24px;
}
.card__body .tit {
  font-size: 24px;
  margin-bottom: 10px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.card__body .desc {
  font-size: 18px;
  line-height: 1.4;
  color: #666;
  margin-bottom: 20px;
  font-weight: 300;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
}
@media (max-width: 960px) {
  .card__inner {
    flex-wrap: wrap;
  }
  .card {
    width: 49%;
  }
  .card:last-child {
    display: none;
  }
}
@media (max-width: 600px) {
  .card {
    width: 100%;
  }
  .card:first-child {
    margin-bottom: 20px;
  }
  .card__body {
    padding: 20px;
  }
  .card__body .desc {
    font-size: 16px;
  }
}
</style>