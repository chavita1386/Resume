<template>
  <div class="aside">    
    <div class="content--overflow">
      <div class="photo">
        <img src="../../assets/profile-md.jpg" alt="Salvador Rocha" class="photo__img">
      </div>
      <div class="contact">
        <h2 class="title" :class="menu ? 'in': ''"><span>Contact</span></h2>
        <ul class="contact__list">
          <li class="contact__li">{{cell}}</li>
          <li class="contact__li">{{email}}</li>
          <li class="contact__li">{{city}}, {{country}}</li>
          <li class="contact__li">C.P. {{postcode}}</li>
        </ul>
      </div>

      <div class="education">
        <h2 class="title" :class="menu ? 'in': ''"><span>Education</span></h2>
        <app-education v-for="item in educations" :key="item.idEducation" :title="item.title" :school="item.school" :time="item.time"></app-education>
      </div>      

      <!-- <div>
        <h2 class="title">Skills</h2>
        <app-skills :skills="skills"></app-skills>
      </div> -->

    </div>

  </div>
</template>

<script>
import appEducation from './appEducation.vue';
import appSkills  from './appSkills.vue';
export default {
  props: ['cell', 'email', 'city', 'state', 'country', 'postcode', 'educations', 'skills', 'menu'],
  components: { appEducation, appSkills },
  data() {
    return {

    }
  },
  methods: {
    
  }

}
</script>

