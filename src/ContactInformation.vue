<template>
    <fieldset>
        <legend>{{msg}}</legend>
        <p>Телефон: <input type="tel" name="phone" pattern="[0-9]{3}-[0-9]{2}-[0-9]{2}" placeholder="111-11-11" v-model="message.value1" @focus="saveMessage"/>
        <p>E-mail: <input type="email" placeholder="e-mail" v-model="message.value2" @focus="saveMessage"/></p>
        <p>Скайп: <input type="text" placeholder="skype" v-model="message.value3" @focus="saveMessage"/></p>
        <p>Телеграмм: <input type="text" placeholder="telegram" v-model="message.value4" @focus="saveMessage"/></p>
        <p>Сайт: <input type="url" placeholder="URL" v-model="message.value5" @focus="saveMessage"/></p>
    </fieldset>
</template>
<script>
export default {
name: "ContactInformation",
  props: {
    msg: String
  },
  data() {
    return {
      message: {
        value1: "",
        value2: "",
        value3: "",
        value4: "",
        value5: ""
      }
    }
  },
  methods: {
    saveMessage: function() {
      this.$emit('message', this.message);
    }
  }
}
</script>
<style scoped>
legend {
    color:rgb(66, 6, 143);
    font-size: 25px;
}
p {
    color:rgb(4, 3, 70);
    font-size: 20px;
}
</style>