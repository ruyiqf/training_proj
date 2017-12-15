<template>

<div id="firstcomponent">
    <h1> I am a title</h1>
    <a> written by {{ author }}</a>
    <ul>
        <li><router-link to="/LandingPage">点击我</router-link></li>
    </ul>
    <p>Using mustaches: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    <span>Only one time change msg: {{msg}}</span>
    <br>
    <input v-model="msg">
    <p>Original message: "{{message}}"</p>
    <p>Computed reverse message: "{{reversedMessage}}"</p>
</div>

</template>

<script type="text/javascript">
export default {
    data() {
      return {
        author: "occeancalmcool",
        rawHtml: "<span style='color:red'>This should be red.</span>",
        msg: "euxyacg",
        message: "euxyacg"
      }
    },
    computed: {
        reversedMessage: function() {
          return this.message.split('').reverse().join('')
        }
    }
}
</script>
