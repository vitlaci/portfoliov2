<template>
  <div class="tokyo_tm_contact">
    <div class="tokyo_tm_title">
      <div class="title_flex">
        <div class="left">
          <span>Contact</span>
          <h3>Get in Touch</h3>
        </div>
      </div>
    </div>
    <!-- End Title -->

    <div class="map_wrap">
      <iframe
        id="gmap_canvas"
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d144547.76873239095!2d8.323053086846219!3d55.52263380480711!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x464b20a619e30ce9%3A0xdde847ab4e4ae9d1!2sEsbjerg!5e0!3m2!1sen!2sdk!4v1650571512423!5m2!1sen!2sdk"
        frameborder="0"
        scrolling="no"
        marginheight="0"
        marginwidth="0"
      ></iframe>
    </div>
    <!-- End Google Map -->

    <div class="fields">
      <ValidationObserver v-slot="{ handleSubmit }">
        <form class="contact_form" @submit.prevent="handleSubmit(onSubmit)">
          <div class="first">
            <ul>
              <ValidationProvider
                name="name"
                rules="required"
                v-slot="{ errors }"
              >
                <li>
                  <input
                    v-model="formData.name"
                    type="text"
                    placeholder="Name"
                    autocomplete="off"
                  />
                  <span class="inpur-error">{{ errors[0] }}</span>
                </li>
              </ValidationProvider>

              <ValidationProvider
                name="email"
                rules="required|email"
                v-slot="{ errors }"
              >
                <li>
                  <input
                    type="text"
                    rules="required|email"
                    v-model="formData.email"
                    placeholder="email"
                  />
                  <span class="inpur-error">{{ errors[0] }}</span>
                </li>
              </ValidationProvider>
              <ValidationProvider
                name="message"
                rules="required"
                v-slot="{ errors }"
              >
                <li>
                  <textarea
                    v-model="formData.message"
                    placeholder="Message"
                  ></textarea>
                  <span class="inpur-error">{{ errors[0] }}</span>
                </li>
              </ValidationProvider>
            </ul>
          </div>
          <div class="tokyo_tm_button">
            <button type="submit" class="ib-button">Send Message</button>
          </div>
        </form>
      </ValidationObserver>
    </div>
    <!-- END FIELDS -->
  </div>
</template>

<script>
  import { ValidationObserver } from "vee-validate";
  import { ValidationProvider } from "vee-validate/dist/vee-validate.full.esm";
  export default {
    components: {
      ValidationObserver,
      ValidationProvider,
    },
    data() {
      return {
        formData: {
          name: "",
          email: "",
          message: "",
        },
      };
    },
    methods: {
      onSubmit() {
        console.log(this.formData);
      },
    },
  };
</script>
