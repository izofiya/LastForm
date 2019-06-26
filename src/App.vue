<template>
  <div class="container" v-if="isActive == true">
    <h1>{{ msg }}</h1>
    <Progress msg="Please fill out the form"></Progress>
    <form v-on:submit.prevent="onSubmit" >
      <TotalInformation msg="Total information" @message="displayMessage"></TotalInformation>
      <Education msg="Education" @message="displayMessageEduc"></Education>
      <ContactInformation msg="Contact Information" @message="displayMessageContact"></ContactInformation>
      <UploadPhoto msg="Upload a photo"></UploadPhoto>
     <input type="submit"  v-model="Submit">
    </form>
  </div>
  <div class="info" v-else>
      <ul>
        <li v-for="input in inputs">{{input}}</li>
      </ul>
      <ul>
        <li v-for="input in inputsEduc">{{input}}</li>
      </ul>
      <ul>
        <li v-for="input in inputsContact">{{input}}</li>
      </ul>
  </div>
</template>
<script>
import Progress from './Progress';
import TotalInformation from './TotalInformation';
import Education from './Education';
import ContactInformation from './ContactInformation';
import UploadPhoto from './UploadPhoto';

export default {
  data() {
    return {
      msg: "Form to fill",
      inputs: {},
      inputsEduc: {},
      inputsContact: {},
      isActive: true
    }
  },
  methods: {
    onSubmit: function() {
      this.isActive = false;
    },
    displayMessage: function(message) {
      this.inputs = message;
    },
    displayMessageEduc: function(message) {
      this.inputsEduc = message;
    },
    displayMessageContact: function(message) {
      this.inputsContact = message;
    }
  },
  components: {
    Progress,
    TotalInformation,
    Education,
    ContactInformation,
    UploadPhoto
  }
}
</script>
<style>
  .container{
    color: rgb(94, 4, 4);
  }
</style>

