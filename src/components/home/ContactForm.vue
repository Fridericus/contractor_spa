<template>
  <v-card flat class="pa-5">

    <v-form flat style=""
      ref="form"
      v-model="valid"
      lazy-validation
    >
      <v-text-field
        v-model="name"
        outlined
        :error-messages="nameErrors"
        :counter="10"
        label="Name"
        required
        @input="$v.name.$touch()"
        @blur="$v.name.$touch()"
      ></v-text-field>

      <v-text-field
        v-model="email"
        outlined
        :error-messages="emailErrors"
        label="E-mail"
        required
        @input="$v.email.$touch()"
        @blur="$v.email.$touch()"
      ></v-text-field>

      <v-text-field
        v-model="phone"
        outlined
        :error-messages="phoneErrors"
        label="Phone"
        required
        @input="$v.phone.$touch()"
        @blur="$v.phone.$touch()"
      ></v-text-field>

      <v-textarea
        v-model="comments"
        clearable
        outlined
        label="Comments"
      ></v-textarea>
      
      <v-btn
        color="primary"
        @click="submit()"
        tile
        block
      >
        Submit
      </v-btn>

      <v-overlay
        :absolute="absolute"
        :opacity="opacity"
        :value="overlay"
        :z-index="zIndex"
      >

        <v-progress-circular
          :value="progress"
          :size="100"
          color="primary"
          indeterminate
        ></v-progress-circular>

        <div>
          <v-alert
            :value="alert"
            :color="alertColor"
            dark
            border="top"
            transition="scale-transition"
          >
          {{ alertMessage }}
            <v-btn
              color="primary"
              @click="alert = !alert, overlay = !overlay"
              class="mt-4"
            >
              Return
            </v-btn>          
          </v-alert>
        </div>

      </v-overlay>

    </v-form>

  </v-card>
</template>

<script>
  import { validationMixin } from 'vuelidate'
  import { required, maxLength, minLength, email } from 'vuelidate/lib/validators'

  export default {
    mixins: [validationMixin],

    validations: {
      name: { required, maxLength: maxLength(10)},
      email: { required, email },
      phone: { required, minLength: minLength(9)},
      comments: { },
    },

    data: () => ({
      name: '',
      email: '',
      phone: '',
      comments: '',
      absolute: true,
      opacity: 0.46,
      overlay: false,
      zIndex: 5,
      returnMessage: '',
      alert: false,
      alertMessage: 'Your request has been submitted sucessfully - someone will be in contact shortly!',
      alertColor: "green",
      progress: false
    }),

    computed: {
      nameErrors () {
        const errors = []
        if (!this.$v.name.$dirty) return errors
        !this.$v.name.maxLength && errors.push('Name must be at most 10 characters long')
        !this.$v.name.required && errors.push('Name is required.')
        return errors
      },
      phoneErrors () {
        const errors = []
        if (!this.$v.phone.$dirty) return errors
        !this.$v.phone.minLength && errors.push('Invalid phone number')
        !this.$v.phone.required && errors.push('Phone number is required.')
        return errors
      },
      emailErrors () {
        const errors = []
        if (!this.$v.email.$dirty) return errors
        !this.$v.email.email && errors.push('Must be valid e-mail')
        !this.$v.email.required && errors.push('E-mail is required')
        return errors
      },
    },

    methods: {
      submit () {
        this.$v.$touch()
        if (this.$v.$invalid) {
          this.submitStatus = 'ERROR'

        } else {
          // do your submit logic here
          this.submitStatus = 'PENDING'
          this.overlay = !this.overlay;
          this.$axios.post('https://formspree.io/yourlinkhere', {
            name: this.name,
            email: this.email,
            phone: this.phone,
            comments: this.comments
          })
            .then((responce) => {
              this.returnMessage = responce.data;
              this.alert = !this.alert;
              this.name = '';
              this.email = '';
              this.phone = '';
              this.comments = '';              
            });
          
          setTimeout(() => {
            this.submitStatus = 'OK'

          }, 500)
        } 
      },
    },
  }
</script>

