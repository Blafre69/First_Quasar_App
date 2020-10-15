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
                    />
                </q-card-actions>
            </q-card>
        </div>
    </div>
    </q-page>
</template>

<script>
export default {
  name: 'Sign In',
  data () {
    return {
      email: '',
      password: ''
    }
  }
}
</script>
