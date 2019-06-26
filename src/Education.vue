<template>
    <fieldset>
        <legend>{{msg}}</legend>
        <p>Учреждение образования: <input type="text" placeholder="Ваше образование" v-model="message.value1" @focus="saveMessage"/></p>
        <p>Факультет: <input type="text" placeholder="Ваш факультет" v-model="message.value2" @focus="saveMessage"/></p>
        <p>Специализация: <input type="text" placeholder="Ваша специализация" v-model="message.value3" @focus="saveMessage"/></p>
        <p>Год завершения: <input type="month" name="monthYear" v-model="message.value4" @focus="saveMessage"/></p>
    </fieldset>
</template>
<script>
export default {
name: "Education",
  props: {
    msg: String
  },
  data() {
    return {
      message: {
        value1: "",
        value2: "",
        value3: "",
        value4: ""
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