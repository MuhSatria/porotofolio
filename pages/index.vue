<template>
  <div class="page">
    <div class="header-logo">
      <div class="logo">Logo</div>
    </div>
    <div class="back-top" @click="backToTop()">
      <img src="@/assets/icons/Icon-back-left-outline.svg" alt="">
    </div>
    <div class="navigation">
      <input type="checkbox" class="navigation__checkbox" id="nav-toggle" />

      <label for="nav-toggle" class="navigation__button">
        <span class="navigation__icon">&nbsp;</span>
      </label>

    </div>
    <div class="welcome-page" id="welcome">
      <div class="box-content">
        <div class="box-content__desc">
          <h4>Hi</h4>
          <h2 class="title-header">I'm Muhammad Satria</h2>
          <p class="desc">Frontend Web Developer / UI Designer</p>
          <nuxt-link to="#" class="button-custom">
            <span>Know More</span>
          </nuxt-link>
        </div>
      </div>
      <!-- show hanya di dekstop, dan saat di scroll 400, cek javascript -->
      <div class="box-about">
        <h2 class="box-about__title">About Me</h2>
        <p class="box-about__desc">Saya dapat merumuskan suatu masalah dan menganalisis data untuk membuat sebuah konsep wireframe model apps / web design, saya menggunakan beberapa tools seperti Adoble Photoshop, Illustrator, Adobe XD, Figma inVision dan Marvelapp. <br /> <br /> Selain itu saya juga sangat meminati bidang Frontend Web Developer, di project-project sebelumnya saya menggunakan Vue / Nuxt, saat ini saya sangat tertarik untuk membuat animasi dengan css dan javascript</p>
      </div>
    </div>
    <div class="about-page">
      About
    </div>
    <div class="education-page">
      <div class="logo-page">
        Education
      </div>
      <div class="wrapper">
        <div
          v-for="(educations, index_edu) in education"
          :key="index_edu"
          :id="education[index_edu].id"
          class="col">
          <div class="card">
            <div class="card__header">
              <span>{{ education[index_edu].year }}</span>
            </div>
            <div class="card__body">
              <p class="title">{{ education[index_edu].name }}</p>
              <p class="department">{{ education[index_edu].department }}</p>
              <p class="options">{{ education[index_edu].options }}</p>
            </div>
          </div>
        </div>
      </div>
      <!-- <div class="swipe-wrapper">
        <div
          v-for="(educations, index_edu) in education"
          :key="index_edu"
          :id="education[index_edu].id"
          class="card-slider">
          <div class="card-slider__header">
            <span>{{ education[index_edu].year }}</span>
          </div>
          <div class="card-slider__body">
            <p class="title">{{ education[index_edu].name }}</p>
            <p class="department">{{ education[index_edu].department }}</p>
            <p class="options">{{ education[index_edu].options }}</p>
          </div>
        </div>
      </div> -->
      <div class="box-skill">
        <h1 class="box-skill__title">Skill</h1>
        <div class="box-grid">
          <div
            v-for="(skill_item, index_skill) in skill"
            :key="index_skill"
            class="card">
              <img :src="require(`~/assets/icons/${skill[index_skill].icon}.svg`)" alt="">
              <!-- <p style="text-align: center">{{ skill[index_skill].name }}</p> -->
            </div>
        </div>
      </div>
    </div>
    <div class="experience-page" id="experience">
      <div class="box-content">
        <div class="header-experince" id="headerExperienc">
          <p class="menu-experience" @mouseenter="showClick()">Experience</p>
          <div class="box-stage" id="showBtn">
            <span class="click-btn bounce-normal" @click="showExperience()">Click here</span>
          </div>
        </div>
        <div class="box-data" id="experience-data">
          <div class="wrapper">
            <div
              v-for="(experienc_data, index_expe) in experience"
              :key="index_expe"
              class="col">
              <div class="card">
                <div class="card__header">
                  <span>{{ experience[index_expe].year }}</span>
                </div>
                <div class="card__body">
                  <p class="card__body__company">{{ experience[index_expe].company }}</p>
                  <p class="card__body__text">{{ experience[index_expe].name }}</p>
                  <p class="card__body__text">{{ experience[index_expe].job }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="box-other">
        <p class="box-other__items">Social Media</p>
        <p class="box-other__items">Hobby</p>
        <p class="box-other__items">Contact</p>
      </div>
    </div>
    <div class="overlay" id="overlayBg"></div>
  </div>
</template>

<script>
import anime from 'animejs'
export default {
  data () {
    return {
      title: 'Muhammad Satria',
      education: [
        {
          id: 'smk',
          name: 'SMK Muhammadiyah 1 Sukoharjo',
          year: '2012-2015',
          department: 'Rekayasa Perangkat Lunak',
          options: ['html', 'php', 'mysql', 'visual basic', 'adobe photoshop', 'adobe illustrator']
        },
        {
          id: 'bp2ip',
          name: 'BP2IP Tangerang',
          year: '2015',
          department: 'Teknik Mesin'
        },
        {
          id: 'binarUi',
          name: 'Binar Academy Batch 6 Yogyakarta',
          year: '2018',
          department: 'UI / UX',
          options: ['Konsep Product', 'Analisis Data', 'Resarch', 'Wireframe', 'Scrum', 'Flow Chart', 'Lo-fi & Hi-fi Design Apps & Website']
        },
        {
          id: 'binarCode',
          name: 'Binar Academy Plus Batch 1 Bsd Tangerang',
          year: '2018-2019',
          department: 'Fullstack Web Developer',
          options: ['Java', 'Api Documentasi', 'Git', 'Html', 'Javascript', 'Css', 'Mysql', 'ReactJs', 'Postman', 'Swager']
        }
      ],
      skill: [
        {name: 'Html', icon: 'html'},
        {name: 'Css', icon: 'css'},
        {name: 'Js', icon: 'js'},
        {name: 'Bootstrap', icon: 'bootstrap'},
        {name: 'Vue', icon: 'Vue'},
        {name: 'Adobe AI', icon: 'adobe_ai'},
        {name: 'Adobe PS', icon: 'adobe_ps'},
        {name: 'Adobe XD', icon: 'adobe_xd'},
        {name: 'Figma', icon: 'figma'}
      ],
      experience: [
        {
          name: 'Oiler KM Kota Bagan',
          company: 'Pt Sinar Pagoda',
          year: '2016',
          job: 'Marine Engine Maintace'
        },
        {
          name: 'Freelancer',
          company: 'Self Employed',
          year: '2018',
          job: 'Design Leandingpage website, icon, Bussines card, Banner & pamflet'
        },
        {
          name: 'Frontend Developer',
          company: 'Onero Solution',
          year: '2019 - 2020',
          job: 'Build Website & Mobile Apps with Quasar Framework'
        },
        {
          name: 'Frontend Web Developer',
          company: 'PT Bikin.co',
          year: '3 Bulan Project',
          job: 'Sliceing UI Design to Html css code'
        }
      ]
    }
  },
  head () {
    return {
      title: this.title + ' | Portofolio'
    }
  },
  mounted () {
    window.addEventListener('scroll', this.welcomeHandle)
    window.addEventListener('scroll', this.showbacktoTop)
    window.addEventListener('scroll', this.animationExperience)
    console.log('height body ', document.body.scrollHeight)
    console.log('id experience hieght ', document.getElementById('experience').offsetTop)
  },
  methods: {
    welcomeHandle () {
      // const welcome = document.querySelector('.welcome-page')
      const menuHeader = document.querySelector('.box-content')
      const aboutInfo = document.querySelector('.box-about')
      const distance = window.scrollY

      menuHeader.style.transform = 'translateY(' + distance * -.8 + 'px)'
      
      if (distance >= 400) {
        aboutInfo.style.opacity = '1';
        aboutInfo.style.transform = 'translateY(' + -200 + 'px)'
      } else {
        aboutInfo.style.opacity = '0';
        aboutInfo.style.transform = 'translateY(' + 0 + 'px)'
      }
    },

    overCardEducation (id) {
      const cardBox = document.getElementById(id)
      const overlayBg = document.getElementById('overlayBg')

      cardBox.classList.add('float-card')
      overlayBg.classList.add('show-overlay')
      console.log('masuk')
    },

    removeCardEducationHover (id) {
      const cardBox = document.getElementById(id)
      const overlayBg = document.getElementById('overlayBg')

      cardBox.classList.remove('float-card')
      overlayBg.classList.remove('show-overlay')
      console.log('keluar')
    },
    animationExperience () {
      const textTarget = document.querySelector('.menu-experience')
      const targetHeight = document.getElementById('experience').offsetTop
      const distance = window.scrollY

      // 1538
      if (distance >= targetHeight - 400) {
        textTarget.classList.add('show-text')
      }
    },
    showClick () {
      const textTarget = document.getElementById('showBtn')
      textTarget.style.opacity = '1'
    },
    showExperience () {
      const targetUp = document.getElementById('headerExperienc')
      const hideBtnClick = document.getElementById('showBtn')
      const expericneData = document.getElementById('experience-data')

      targetUp.style.transform = 'translateY(' + -250 + 'px)'
      hideBtnClick.style.opacity = '0'
      hideBtnClick.style.visibility = 'hidden'
      setTimeout(() => {
        expericneData.style.transform = 'translateY(' + -250 + 'px)'
        expericneData.style.opacity = '1'
        expericneData.style.visibility = 'visible'
      }, 500)
    },
    animationText () {
      var textTarget = document.querySelector('.menu-experience')
      textTarget.innerHTML = textTarget.textContent.replace(/\S/g, "<span class='letter'>$&</span>")
      anime.timeline({ loop: false }).add({
          target: '.menu-experience .letter',
          opacity: [0,1],
          easing: "easeInOutQuad",
          duration: 2250,
          delay: (el, i) => 150 * (i+1)
        }).add({
          targets: '.menu-experience',
          opacity: 0,
          duration: 1000,
          easing: "easeOutExpo",
          delay: 1000
        })
    },

    // back to top function
    showbacktoTop () {
      const elementTop = document.querySelector('.back-top')
      const distance = window.scrollY

      if (distance > 100) {
        elementTop.style.visibility = 'visible'
        elementTop.style.opacity = '1'
      } else {
        elementTop.style.visibility = 'hidden'
        elementTop.style.opacity = '0'
      }
    },
    backToTop () {
      const toTop = document.documentElement.scrollTop || document.body.scrollTop

      if (toTop > 0) {
        window.requestAnimationFrame(this.backToTop)
        window.scrollTo(0, toTop - toTop / 8)
      }
    }
  },
  beforeDestroy () {
    window.removeEventListener('click', this.welcomeHandle)
    window.removeEventListener('click', this.showbacktoTop)
    window.addEventListener('scroll', this.animationExperience)
  }
}
</script>


// offsite 400 about page to top