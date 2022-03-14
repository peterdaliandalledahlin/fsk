<template>
  <v-container>
      <form>
        <v-text-field
        v-model="firstname"
        :error-messages="firstnameErrors"
        :counter="10"
        label="Firstname"
        required
        @input="$v.firstname.$touch()"
        @blur="$v.firstname.$touch()"
        ></v-text-field>
        <v-text-field
        v-model="lastname"
        :error-messages="lastnameErrors"
        :counter="10"
        label="Lastname"
        required
        @input="$v.lastname.$touch()"
        @blur="$v.lastname.$touch()"
        ></v-text-field>
        <v-select
        v-model="selectGender"
        :items="itemsGender"
        :error-messages="selectGenderErrors"
        label="Gender"
        required
        @change="$v.selectGender.$touch()"
        @blur="$v.selectGender.$touch()"
        ></v-select>
        <v-select
        v-model="selectCountry"
        :items="itemsCountry"
        :error-messages="selectCountryErrors"
        label="Country"
        required
        @change="$v.selectCountry.$touch()"
        @blur="$v.selectCountry.$touch()"
        ></v-select>

        <v-menu
        ref="menuBirthday"
        v-model="menuBirthday"
        :close-on-content-click="false"
        :nudge-right="40"
        transition="scale-transition"
        offset-y
        min-width="290px"
      >
        <template v-slot:activator="{ on }">
          <v-text-field
            v-model="dateBirthday"
            :error-messages="dateBirthdayErrors"
            label="Birthday date"
            prepend-icon="mdi-calendar"
            readonly
            v-on="on"
          ></v-text-field>
        </template>
        <v-date-picker
          ref="picker"
          v-model="dateBirthday"
          :max="new Date().toISOString().substr(0, 10)"
          min="1920-01-01"
          @change="save"
        ></v-date-picker>
      </v-menu>

    <v-text-field
        v-model="email"
        :error-messages="emailErrors"
        label="E-mail"
        required
        @input="$v.email.$touch()"
        @blur="$v.email.$touch()"
    ></v-text-field>

        <v-text-field
            v-model="phonenumber"
            :error-messages="phonenumberErrors"
            label="Telefonnummer"
            required
            @input="$v.phonenumber.$touch()"
            @blur="$v.phonenumber.$touch()"
        ></v-text-field>

        <v-text-field
            v-model="address"
            :error-messages="addressErrors"
            label="Adress"
            required
            @input="$v.address.$touch()"
            @blur="$v.address.$touch()"
        ></v-text-field>

        <v-text-field
            v-model="zipcode"
            :error-messages="zipcodeErrors"
            label="Postnummer"
            required
            @input="$v.zipcode.$touch()"
            @blur="$v.zipcode.$touch()"
        ></v-text-field>

        <v-text-field
            v-model="city"
            :error-messages="cityErrors"
            label="Ort"
            required
            @input="$v.city.$touch()"
            @blur="$v.city.$touch()"
        ></v-text-field>

        <v-checkbox
        v-model="checkbox"
        :error-messages="checkboxErrors"
        label="Do you agree?"
        required
        @change="$v.checkbox.$touch()"
        @blur="$v.checkbox.$touch()"
        ></v-checkbox>

        <v-btn
        class="mr-4"
        @click="submit"
        >
        submit
        </v-btn>
        <v-btn @click="clear">
        clear
        </v-btn>
    </form>
  </v-container>
</template>

<script>
  import { validationMixin } from 'vuelidate'
  import { required, maxLength, email } from 'vuelidate/lib/validators'

  export default {
      name: 'membership',
      mixins: [validationMixin],
      validations: {
      firstname: { required, maxLength: maxLength(10) },
      lastname: { required, maxLength: maxLength(10) },
      dateBirthday: { required },
      email: { required, email },
      phonenumber: { required },
      address: { required },
      zipcode: { required, maxLength: maxLength(5) },
      city: { required },
      selectGender: { required },
      selectCountry: { required },
      checkbox: {
        checked (val) {
          return val
        },
      },
    },

    data: () => ({
      activePicker: null,
      dateBirthday: null,
      menuBirthday: false,
      firstname: '',
      lastname: '',
      email: '',
      phonenumber: '',
      address: '',
      zipcode: '',
      city: '',
      selectGender: null,
      selectCountry: null,
      itemsGender: [
        'Man',
        'Kvinna',
        'Hen',
      ],
      itemsCountry: [
        'Sverige',
        'Norge',
        'Suomi',
      ],
      checkbox: false,
    }),

    watch: {
        menuBirthday (val) {
        val && this.$nextTick(() => (this.$refs.picker.activePicker = 'YEAR'))
    },
    },

    computed: {
      checkboxErrors () {
        const errors = []
        if (!this.$v.checkbox.$dirty) return errors
        !this.$v.checkbox.checked && errors.push('You must agree to continue!')
        return errors
      },
      selectGenderErrors () {
        const errors = []
        if (!this.$v.selectGender.$dirty) return errors
        !this.$v.selectGender.required && errors.push('Gender is required')
        return errors
      },
      selectCountryErrors () {
        const errors = []
        if (!this.$v.selectCountry.$dirty) return errors
        !this.$v.selectCountry.required && errors.push('Country is required')
        return errors
      },
      firstnameErrors () {
        const errors = []
        if (!this.$v.firstname.$dirty) return errors
        !this.$v.firstname.maxLength && errors.push('Firstname must be at most 10 characters long')
        !this.$v.firstname.required && errors.push('Name is required.')
        return errors
      },
      lastnameErrors () {
        const errors = []
        if (!this.$v.lastname.$dirty) return errors
        !this.$v.lastname.maxLength && errors.push('Lastname must be at most 10 characters long')
        !this.$v.lastname.required && errors.push('Name is required.')
        return errors
      },
      emailErrors () {
        const errors = []
        if (!this.$v.email.$dirty) return errors
        !this.$v.email.email && errors.push('Must be valid e-mail')
        !this.$v.email.required && errors.push('E-mail is required')
        return errors
      },
      phonenumberErrors () {
        const errors = []
        if (!this.$v.phonenumber.$dirty) return errors
        !this.$v.phonenumber.required && errors.push('Phone is required')
        return errors
      },
      dateBirthdayErrors () {
        const errors = []
        if (!this.$v.dateBirthday.$dirty) return errors
        !this.$v.dateBirthday.required && errors.push('Birthday is required')
        return errors
      },
      addressErrors () {
        const errors = []
        if (!this.$v.address.$dirty) return errors
        !this.$v.address.required && errors.push('Address is required')
        return errors
      },
      zipcodeErrors () {
        const errors = []
        if (!this.$v.zipcode.$dirty) return errors
        !this.$v.zipcode.maxLength && errors.push('Zipcode must be 5 characters long')
        !this.$v.zipcode.required && errors.push('Zipcode is required')
        return errors
      },
      cityErrors () {
        const errors = []
        if (!this.$v.city.$dirty) return errors
        !this.$v.city.required && errors.push('Address is required')
        return errors
      },
    },

    methods: {
      save (date) {
        this.$refs.menuBirthday.save(date)
      },
      submit () {
        this.$v.$touch()
      },
      clear () {
        this.$v.$reset()
        this.firstname = ''
        this.lastname = ''
        this.email = ''
        this.selectGender = null
        this.selectCountry = null
        this.phonenumber = ''
        this.address = ''
        this.zipcode = ''
        this.city = ''
        this.checkbox = false
      },
    },
  }
</script>

<style>

</style>