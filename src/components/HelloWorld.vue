<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>{{ now }}</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
	data() {
		return {
			now:  this.getNow()
		};
	},
  created() {
    setInterval(() => {
      this.getNow();
    }, 1000)
  },
  methods: {
    getNow: function() {
      const today = new Date();
      const date = today.getFullYear() + '-' + (today.getMonth() + 1) + '-' + today.getDate();
      const time = ("0" + today.getHours()).slice(-2) + ":" + ("0" + today.getMinutes()).slice(-2) + ":" +  ("0" + today.getSeconds()).slice(-2) ;
      const dateTime = date + ' ' + time;
      this.now = dateTime;
    }
  }
};
</script>