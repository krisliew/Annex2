<template>
  <section id="Contact">
    <div id="contactSeparator">
      <h5>
        If you are interested in the services that we provide, please leave us a
        message below.
      </h5>
    </div>
    <div class="container">
      <div class="row">
        <div class="col-lg-8 mx-auto">
          <h2>Contact us</h2>
          <p class="lead">Please fill in all * field below</p>
          <b-form @submit.prevent="onSubmit">
            <div class="form-group">
              <b-form-input
                id="name"
                v-model="name"
                placeholder="Your Name *"
              />
            </div>
            <div class="form-group">
              <b-form-input
                id="email"
                v-model="email"
                type="email"
                placeholder="Your Email *"
              />
            </div>
            <div class="form-group">
              <b-form-select id="enquiryType" v-model.number="enquiryType">
                <b-form-select-option
                  v-for="et in enquiryTypes"
                  :key="et.id"
                  :value="et.id"
                >
                  {{ et.option }}</b-form-select-option
                >
              </b-form-select>
            </div>
            <div class="form-group">
              <b-form-textarea
                id="message"
                v-model="message"
                placeholder="Your Message*"
              ></b-form-textarea>
            </div>

            <div v-if="errors.length" id="errorMSG">
              <b>Please correct the following error(s):</b>
              <ul>
                <li v-for="error in errors" :key="error">{{ error }}</li>
              </ul>
            </div>
            <div class="form-group">
              <b-button variant="primary" type="submit">Submit</b-button>
            </div>
          </b-form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      name: null,
      email: null,
      message: null,
      enquiry: null,
      enquiryType: 0,
      enquiryTypes: [
        {
          id: 0,
          option: 'Select a specific enquiry *',
        },
        {
          id: 1,
          option: 'Business',
        },
        {
          id: 2,
          option: 'Service/Technical Helpdesk',
        },
        {
          id: 3,
          option: 'Improvement',
        },
        {
          id: 4,
          option: 'Others',
        },
      ],
      errors: [],
    }
  },
  methods: {
    onSubmit() {
      this.errors = []
      if (this.name && this.email && this.message && this.enquiryType !== 0) {
        const enquireSubmit = {
          name: this.name,
          email: this.email,
          message: this.message,
          enquiry: this.enquiryType,
        }
        this.$emit('review-submitted', enquireSubmit)
        this.name = null
        this.email = null
        this.message = null
        this.enquiryType = 0
      } else {
        if (!this.name) this.errors.push('Name required')
        if (!this.email) this.errors.push('Email required')
        if (this.enquiryType === 0)
          this.errors.push('Specific enquiry required')
        if (!this.message) this.errors.push('Message required')
      }
    },
  },
}
</script>

<style scoped>
section {
  padding-bottom: 50px;
  min-height: 100vh;
}
/*-----------Contact Us Section---------------*/
#contactSeparator {
  padding-top: 30px;
  padding-bottom: 30px;
  background-color: rgba(0, 0, 41, 0.9);
  color: white;
  text-align: center;
  margin-bottom: 40px;
}
#Contact .row {
  text-align: center;
  margin-left: auto;
  margin-right: auto;
}
#Contact input,
#Contact textarea,
#Contact select {
  min-width: 250px;
  height: 50px;
}
#Contact textarea {
  height: 200px;
}
#Contact input[type='submit'] {
  width: 150px;
  text-indent: 0px;
}
#errorMSG {
  color: red;
  margin-left: auto;
  margin-right: auto;
  width: 300px;
}
#errorMSG li {
  text-align: left;
  text-indent: 50px;
}
#enquiryType option:first-child {
  display: none;
}
</style>
