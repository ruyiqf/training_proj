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
    <p>Original message: "{{msg}}"</p>
    <p>Display current time: "{{nowtime}}"</p>
    <p>Reversed message: "{{ reversedMessage() }}"</p>
    <p>{{fullName}}</p>
</div>

</template>

<script type="text/javascript">
export default {
    data() {
        return {
            author: "occeancalmcool",
            rawHtml: "<span style='color:red'>This should be red.</span>",
            msg: "euxyacg",
            message: "euxyacg",
            firstName: "Foo",
            lastName: "Bar",
            fullName: "Foo Bar"
        }
    },
    computed: {
        nowtime: function() {
            return new Date().toLocaleString()
        }
    },
    methods: {
        reversedMessage: function() {
            return this.message.split('').reverse().join('')
        }
    },
    watch: {
        firstName: function(val) {
            this.fullName = val + ' ' + this.lastName
        },
        lastName: function(val) {
            this.fullName = this.firstName + ' ' + val
        }
    }

}
</script>
