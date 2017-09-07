<template>
  <div>
    <div class="menu to-m">
      <span class="icon-bars"></span>
    </div>
    <!--      ASIDE     -->
    <aside class="aside item no-padding from-m m-30 l-20 ">
      <div class="content">
        <div class="profile">                  
          <figure class="photo">
            <img src="./assets/profile.jpg" class="photo__img" :alt="name">
          </figure>
        </div>

        <asideTitle title="Contact"></asideTitle>

        <contact :email="email" :cell="cell" :location="location"></contact>

        <social :socialItem="socialNetwork"></social>

        <asideTitle title="Education"></asideTitle>

        <education :lstEducation="education"></education>

        <asideTitle title="Professional Skills"></asideTitle>

        <professional v-for="item in professionalSkills" :technology="item.technology" :percent="item.percent" :key="item.id"></professional>

      </div>
    </aside>

    <!--      HEADER    -->
    <header class="header item main-center s-100 m-70 l-80 to-right no-padding">
      <h1 class="header__title">{{name}}</h1>
    </header>

    <!--      MAIN      -->
    <main class="main item s-100 m-70 l-80 to-right">
      <div class="container">
        <div class="item info">
          <h2 class="info__title">Profile</h2>
          <p class="info__text">
            {{profile}}
          </p>
        </div>
        <div class="item info">
          <h2 class="info__title">Experience</h2>
          <div>
            <h4 class="info__title--h4">NISSAN / SINERSYS </h4>
            <h5 class="info__title--h5">OCTOBER 2015 - DECEMBER 2015</h5>
            <p class="info__text">
              <strong>Senior Developer .NET and Frontend - </strong>
              Testing and improve Software called TAMESIS in ASP.NET 4.5 and SQL Server 2008 and I develop new UI for TAMESIS compatible with Internet Explorer 9 and Google Chrome.
            </p>
          </div>
          <div>
            <h4 class="info__title--h4">FREELANCE</h4>
            <h5 class="info__title--h5">JANUARY 2014 - OCTOBER 2015</h5>
            <p class="info__text">
              <strong>Senior Developer .NET and Frontend - </strong>
              Developer applications (web and desktop) on Microsoft Framework 4.5, for example: a Financial System for the Government , around 15 web pages including a tool to manage them, a Client-Server application to control anothers computers and mange them
            </p>
          </div>
        </div>

        <div class="item info">
          <h2 class="info__title">
            Professional Development
          </h2>
          <div class="container">
            <div class="item m-50">
              <div class="card">
                <h4>Certificate Microsoft Sharepoint 2007 </h4>
                <h5>Aguascalientes, Ags. México</h5>
                <h5>Jan 2010</h5>
              </div>
            </div>
            <div class="item m-50">
              <div class="card">
                <h4>Certificate Microsoft Sharepoint 2007 </h4>
                <h5>Aguascalientes, Ags. México</h5>
                <h5>Jan 2010</h5>
              </div>
            </div>
            <div class="item m-50">
              <div class="card">
                <h4>Certificate Microsoft Sharepoint 2007 </h4>
                <h5>Aguascalientes, Ags. México</h5>
                <h5>Jan 2010</h5>
              </div>
            </div>
            <div class="item m-50">
              <div class="card">
                <h4>Certificate Microsoft Sharepoint 2007 </h4>
                <h5>Aguascalientes, Ags. México</h5>
                <h5>Jan 2010</h5>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>

  </div>
  <!-- <person></person> -->
</template>

<script>
// import person from './components/Person.vue';
// import cabeza from './components/Header.vue';
import asideTitle from './components/AsideTitle.vue';
import contact from './components/Contact.vue';
import social from './components/Social.vue';
import education from './components/Education.vue';
import professional from './components/Professional.vue';
export default {
  components: { asideTitle, contact, social, education, professional },
  data() {
    return {
      name: 'Salvador Rocha Robledo',
      title: 'asdfas',
      email: 'srocha@hotmail.com',
      cell: '4491248400',
      profile: 'I am a web developer with six years of experience in Microsoft .NET Framework and Java as backend and frontend, including three years as lead programmer in the Government of Aguascalientes in which we helped it to improve and change about ten systems. After that I worked as a Freelance about two years developing Web Apps one of them a financial system for the Government, and five Web pages with web Administrator. Lately my approach is as Frontend developer using new technologies like AngularJS, ReactJS, NodeJS, SASS, Stylus, Jade, etc. I am passionate developer with all kinds of technology and I like to learn by myself and share my knowledge with others.',
      location: {
        city: 'Aguascalientes',
        state: 'Aguascalientes',
        postcode: 20256.0,
      },
      socialNetwork:
      [
        {
          idSocialNetwork: 1,
          name: 'twitter',
          url: 'https://twitter.com/chavita1386'
        },
        {
          idSocialNetwork: 2,
          name: 'github',
          url: 'https://github.com/chavita1386'
        },
        {
          idSocialNetwork: 3,
          name: 'linkedin',
          url: 'https://linkedin.com/chavita1386'
        }
      ],
      education: [{
        idEducation: 1,
        title: 'Degree in Information Technologies',
        school: 'Technological Institute of Aguascalientes',
        time: '2004-2010'
      },
      {
        idEducation: 2,
        title: 'Computer Technician',
        school: 'CETIS #155',
        time: '2000-2004'
      }],
      professionalSkills: [{
        id: 1,
        technology: 'FrontEnd',
        percent: 'high',
      },
      {
        id: 2,
        technology: 'Backend',
        percent: 'expert',
      }
      ]
    }
  }
}
</script>

<style src="./styles/style.scss" lang="scss">

</style>
