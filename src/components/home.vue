<template>
  <div class="hello">
    - Bootstrap 모듈 추가 완료
    <p>
      <b-badge variant="primary">Primary</b-badge>
      <b-badge variant="secondary">Secondary</b-badge>
      <b-badge variant="success">Success</b-badge>
      <b-badge variant="danger">Danger</b-badge>
      <b-badge variant="warning">Warning</b-badge>
      <b-badge variant="info">Info</b-badge>
      <b-badge variant="light">Light</b-badge>
      <b-badge variant="dark">Dark</b-badge>
    </p>
    <div>
      <b-alert show>Default Alert</b-alert>

      <b-alert variant="success" show>Success Alert</b-alert>

      <b-alert variant="danger"
               dismissible
               :show="showDismissibleAlert"
               @dismissed="showDismissibleAlert=false">
        Dismissible Alert!
      </b-alert>

      <b-alert :show="dismissCountDown"
               dismissible
               variant="warning"
               @dismissed="dismissCountDown=0"
               @dismiss-count-down="countDownChanged">
        <p>This alert will dismiss after {{dismissCountDown}} seconds...</p>
        <b-progress variant="warning"
                    :max="dismissSecs"
                    :value="dismissCountDown"
                    height="4px">
        </b-progress>
      </b-alert>

      <b-btn @click="showAlert" variant="info" class="m-1">
        Show alert with count-down timer
      </b-btn>
      <b-btn @click="showDismissibleAlert=true" variant="info" class="m-1">
        Show dismissible alert ({{showDismissibleAlert?'visible':'hidden'}})
      </b-btn>
    </div>

    <div>
      <b-button>I am a Button</b-button>
      <b-button href="#">I am a Link</b-button>
    </div>
  </div>

</template>

<script>
  export default {
    name: 'home'
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
