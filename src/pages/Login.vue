<template>
    <q-page
        class="window-height window-width row justify-center bg-image"
    >
    <div class="column">
        <div class="row">
            <h5 class="text-h5 text-black text-center full-width">Sign in</h5>
        </div>
        <div class="row">
            <q-card square class="g-pa-lg shadow-0" style="background:none;">
                <q-card-section>
                    <q-form class="q-gutter-md">
                        <q-input
                            autofocus
                            square
                            filled
                            clearable
                            v-model="email"
                            type="email"
                            label="Email"
                            label-color="black"
                            bg-color="field"
                        >
                            <template v-slot:prepend>
                                <q-icon name="email" color="black"/>
                            </template>
                        </q-input>
                        <q-input
                            autofocus
                            square
                            filled
                            clearable
                            v-model="password"
                            type="password"
                            label="Password"
                            label-color="black"
                            bg-color="field"
                            >
                            <template v-slot:prepend>
                                <q-icon name="lock" color="black"/>
                            </template>
                        </q-input>
                    </q-form>
                </q-card-section>
                <q-card-actions class="q-px-md">
                    <q-btn
                        color="light-blue"
                        unelevated
                        size="lg"
                        class="full-width"
                        label="Sign in"
                        @click='login(email,password)'
                    />
                </q-card-actions>
            </q-card>
        </div>
    </div>
    </q-page>
</template>

<!-- The core Firebase JS SDK is always required and must be listed first -->
<script src="https://www.gstatic.com/firebasejs/7.24.0/firebase-app.js"></script>

<!-- TODO: Add SDKs for Firebase products that you want to use
     https://firebase.google.com/docs/web/setup#available-libraries -->
<script src="https://www.gstatic.com/firebasejs/7.24.0/firebase-analytics.js"></script>

<script>
import firebase from 'firebase/app'
import 'firebase/auth'
import 'firebase/database'
import 'firebase/analytics'

  const firebaseConfig = {
    apiKey: "AIzaSyCO_BL1OsnGQ6VkVqQztJOP4JNCzGjCsos",
    authDomain: "shopping-app-e6b62.firebaseapp.com",
    databaseURL: "https://shopping-app-e6b62.firebaseio.com",
    projectId: "shopping-app-e6b62",
    storageBucket: "shopping-app-e6b62.appspot.com",
    messagingSenderId: "589982855139",
    appId: "1:589982855139:web:cde3f86a2f5a334f9abad6",
    measurementId: "G-2SF9KWL5E9"
  };
  // Initialize Firebase
  firebase.initializeApp(firebaseConfig);
  firebase.analytics();
export default {
  name: 'Sign In',
  data () {
    return {
      email: '',
      password: ''
    }
  },

  methods: {
    login (email, password) {
      firebase.auth().signInWithEmailAndPassword(email, password)
        .then((result) => {
          if (result.user.uid) {
            this.$router.replace({ name: 'shoppinglist' })
          }
        })
        .catch(function (error) {
          var errorMessage = error.message

          this.$q.notify(errorMessage)
        })
      }
  }
}
</script>
