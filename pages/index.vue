<template lang='pug'>
  section.hero.is-fullheight
    .hero-body
      .container
        h1.title
          | Fullheight title
        h2.subtitle
          | Fullheight subtitle
        h1
          | test
        button.button.is-primary(@click="googleLogin()" type='button')
          span.icon
            i.fab.fa-google
          span Login with Google
        button.button.is-danger(@click="setError()")
          span setError

</template>

<script lang="ts">
import { fireBase } from '../plugins/firebase'

interface Result {
  user: {
    displayName: string,
    email: string,
    photoURL: string,
    uid: string,
  }
}

export default {
  
  methods: {
    googleLogin() {
      var provider = new fireBase.auth.GoogleAuthProvider();
      var self = this;
      // @ts-ignore
      fireBase.auth().signInWithPopup(provider).then(function(result: Result) {
        
        // @ts-ignore
        self.$axios.post(
          '/api/users', { 
            name: result.user.displayName,
            email: result.user.email,
            image: result.user.photoURL,
            uid: result.user.uid,
          }
        ).then((res: any) => {
          let userObj = {
            name: res.data.name,
            image: res.data.image,
          }
          // @ts-ignore
          self.$store.dispatch('user/setUser', userObj)
        })
      }).catch(function(error: Error) {
        // @ts-ignore
        self.$store.dispatch('error/setMessage', error.message)
      });
    },
    setError() {
      // @ts-ignore
      this.$store.dispatch('error/setMessage', 'error!!!')
    }
  }
}
</script>

<style>
</style>
