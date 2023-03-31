<template>
  <div id="container" class="grid lg:grid-cols-3 md:grid-cols-1 lg:ml-14 md:space-x-6 lg:space-y-0 sm:space-y-12">

    <!-- Start of Form -->
    <div class="col-span-1">
      <form ref="form" class="rounded-3xl py-8 text-center my-12 md:my-0" @submit.prevent="submitForm">
        <div class="space-y-6">

          <label for="name"></label>
          <input class=" rounded-lg px-6 py-2" type="text" v-model="name" id="name" placeholder="Name" required>
          <div v-if="nameError" class="error">{{ nameError }}</div>

        </div>
        <div class="space-y-6">

          <label for="email"></label>
          <input class=" rounded-lg px-6 py-2" type="email" v-model="email" id="email" placeholder="Email" required>
          <div v-if="emailError" class="error">{{ emailError }}</div>

        </div>
        <div class="space-y-6">

          <label for="phone"></label>
          <input class=" rounded-lg px-6 py-2" type="tel" v-model="phone" id="phone" pattern="0[1-9]\d{8}"
            placeholder="Phone Number (+27)" required>
          <div v-if="phoneError" class="error">{{ phoneError }}</div>

          <br>
          <!-- <span v-if="!valid">Enter Valid S.A Phone number</span> -->

        </div>
        <div class="space-y-6">

          <label for="message"></label>
          <textarea class=" rounded-lg px-6 py-2 h-28" id="message" v-model="message" placeholder="Message"
            required></textarea>
          <div v-if="messageError" class="error">{{ messageError }}</div>
        </div>

        <button class="mt-6 bg-white h-10 rounded-lg" type="submit">Submit</button>

      </form>
    </div>
    <!-- End of Form -->

    <!-- Start of Text Box -->
    <div id="text" class="col-span-2 p-12 bg-white bg-opacity-75 rounded-3xl space-y-8">

      <div class="space-y-6">
        <h2 class="text-4xl">Looking for me?</h2>
        <p class="md:w-96">Trying to contact us? Feel free to fill out the form.
          If that is unsuccessful, then contact us directly:</p>
      </div>
      <div class="grid md:grid-cols-2 sm:grid-cols-1 space-y-6 md:space-y-0">

        <div class="space-y-6">

          <h3>Location 1</h3>
          <ul class="space-y-6">

            <li class="flex space-x-2 items-center">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M9.99996 18.3333C8.86107 18.3333 7.78468 18.1144 6.77079 17.6767C5.7569 17.2389 4.87135 16.6417 4.11413 15.885C3.35746 15.1283 2.76024 14.2431 2.32246 13.2292C1.88468 12.2153 1.66607 11.1389 1.66663 10C1.66663 8.84723 1.88552 7.76723 2.32329 6.76001C2.76107 5.75278 3.35829 4.87112 4.11496 4.11501C4.87163 3.35778 5.75663 2.76056 6.76996 2.32334C7.78329 1.88612 8.85996 1.66723 9.99996 1.66667C11.1527 1.66667 12.2327 1.88556 13.24 2.32334C14.2472 2.76112 15.1288 3.35834 15.885 4.11501C16.6422 4.87167 17.2394 5.75362 17.6766 6.76084C18.1138 7.76806 18.3327 8.84778 18.3333 10V11.2083C18.3333 12.0278 18.0522 12.7258 17.49 13.3025C16.9277 13.8792 16.2366 14.1672 15.4166 14.1667C14.9166 14.1667 14.4513 14.0556 14.0208 13.8333C13.5902 13.6111 13.2361 13.3194 12.9583 12.9583C12.5833 13.3333 12.1422 13.6286 11.635 13.8442C11.1277 14.0597 10.5827 14.1672 9.99996 14.1667C8.84718 14.1667 7.8644 13.7603 7.05163 12.9475C6.23885 12.1347 5.83274 11.1522 5.83329 10C5.83329 8.84723 6.23968 7.86445 7.05246 7.05167C7.86524 6.23889 8.84774 5.83278 9.99996 5.83334C11.1527 5.83334 12.1355 6.23973 12.9483 7.05251C13.7611 7.86528 14.1672 8.84778 14.1666 10V11.2083C14.1666 11.6111 14.2916 11.9269 14.5416 12.1558C14.7916 12.3847 15.0833 12.4994 15.4166 12.5C15.75 12.5 16.0416 12.3853 16.2916 12.1558C16.5416 11.9264 16.6666 11.6106 16.6666 11.2083V10C16.6666 8.18056 16.0102 6.61445 14.6975 5.30167C13.3847 3.98889 11.8188 3.33278 9.99996 3.33334C8.18052 3.33334 6.6144 3.98973 5.30163 5.3025C3.98885 6.61528 3.33274 8.18112 3.33329 10C3.33329 11.8194 3.98968 13.3856 5.30246 14.6983C6.61524 16.0111 8.18107 16.6672 9.99996 16.6667H14.1666V18.3333H9.99996ZM9.99996 12.5C10.6944 12.5 11.2847 12.2569 11.7708 11.7708C12.2569 11.2847 12.5 10.6944 12.5 10C12.5 9.30556 12.2569 8.71528 11.7708 8.22917C11.2847 7.74306 10.6944 7.5 9.99996 7.5C9.30552 7.5 8.71524 7.74306 8.22913 8.22917C7.74302 8.71528 7.49996 9.30556 7.49996 10C7.49996 10.6944 7.74302 11.2847 8.22913 11.7708C8.71524 12.2569 9.30552 12.5 9.99996 12.5Z"
                  fill="black" />
              </svg>
              <p>company@gmail.com</p>
            </li>

            <li class="flex space-x-2 items-center">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M5.51667 8.99167C6.71667 11.35 8.65 13.275 11.0083 14.4833L12.8417 12.65C13.0667 12.425 13.4 12.35 13.6917 12.45C14.625 12.7583 15.6333 12.925 16.6667 12.925C17.125 12.925 17.5 13.3 17.5 13.7583V16.6667C17.5 17.125 17.125 17.5 16.6667 17.5C8.84167 17.5 2.5 11.1583 2.5 3.33333C2.5 2.875 2.875 2.5 3.33333 2.5H6.25C6.70833 2.5 7.08333 2.875 7.08333 3.33333C7.08333 4.375 7.25 5.375 7.55833 6.30833C7.65 6.6 7.58333 6.925 7.35 7.15833L5.51667 8.99167Z"
                  fill="black" />
              </svg>
              <p>+27 (0)12 345 6789</p>
            </li>

            <li class="flex space-x-2 items-center">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M9.99996 1.66667C6.77496 1.66667 4.16663 4.27501 4.16663 7.5C4.16663 11.875 9.99996 18.3333 9.99996 18.3333C9.99996 18.3333 15.8333 11.875 15.8333 7.5C15.8333 4.27501 13.225 1.66667 9.99996 1.66667ZM5.83329 7.5C5.83329 5.20001 7.69996 3.33334 9.99996 3.33334C12.3 3.33334 14.1666 5.20001 14.1666 7.5C14.1666 9.9 11.7666 13.4917 9.99996 15.7333C8.26663 13.5083 5.83329 9.875 5.83329 7.5Z"
                  fill="black" />
                <path
                  d="M9.99996 9.58334C11.1506 9.58334 12.0833 8.6506 12.0833 7.50001C12.0833 6.34941 11.1506 5.41667 9.99996 5.41667C8.84937 5.41667 7.91663 6.34941 7.91663 7.50001C7.91663 8.6506 8.84937 9.58334 9.99996 9.58334Z"
                  fill="black" />
              </svg>

              <p>123 Lorem road
                Ipsum</p>
            </li>

          </ul>

        </div>
        <div class="space-y-6">

          <h3>Location 2</h3>
          <ul class="space-y-6">

            <li class="flex space-x-2 items-center">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M9.99996 18.3333C8.86107 18.3333 7.78468 18.1144 6.77079 17.6767C5.7569 17.2389 4.87135 16.6417 4.11413 15.885C3.35746 15.1283 2.76024 14.2431 2.32246 13.2292C1.88468 12.2153 1.66607 11.1389 1.66663 10C1.66663 8.84723 1.88552 7.76723 2.32329 6.76001C2.76107 5.75278 3.35829 4.87112 4.11496 4.11501C4.87163 3.35778 5.75663 2.76056 6.76996 2.32334C7.78329 1.88612 8.85996 1.66723 9.99996 1.66667C11.1527 1.66667 12.2327 1.88556 13.24 2.32334C14.2472 2.76112 15.1288 3.35834 15.885 4.11501C16.6422 4.87167 17.2394 5.75362 17.6766 6.76084C18.1138 7.76806 18.3327 8.84778 18.3333 10V11.2083C18.3333 12.0278 18.0522 12.7258 17.49 13.3025C16.9277 13.8792 16.2366 14.1672 15.4166 14.1667C14.9166 14.1667 14.4513 14.0556 14.0208 13.8333C13.5902 13.6111 13.2361 13.3194 12.9583 12.9583C12.5833 13.3333 12.1422 13.6286 11.635 13.8442C11.1277 14.0597 10.5827 14.1672 9.99996 14.1667C8.84718 14.1667 7.8644 13.7603 7.05163 12.9475C6.23885 12.1347 5.83274 11.1522 5.83329 10C5.83329 8.84723 6.23968 7.86445 7.05246 7.05167C7.86524 6.23889 8.84774 5.83278 9.99996 5.83334C11.1527 5.83334 12.1355 6.23973 12.9483 7.05251C13.7611 7.86528 14.1672 8.84778 14.1666 10V11.2083C14.1666 11.6111 14.2916 11.9269 14.5416 12.1558C14.7916 12.3847 15.0833 12.4994 15.4166 12.5C15.75 12.5 16.0416 12.3853 16.2916 12.1558C16.5416 11.9264 16.6666 11.6106 16.6666 11.2083V10C16.6666 8.18056 16.0102 6.61445 14.6975 5.30167C13.3847 3.98889 11.8188 3.33278 9.99996 3.33334C8.18052 3.33334 6.6144 3.98973 5.30163 5.3025C3.98885 6.61528 3.33274 8.18112 3.33329 10C3.33329 11.8194 3.98968 13.3856 5.30246 14.6983C6.61524 16.0111 8.18107 16.6672 9.99996 16.6667H14.1666V18.3333H9.99996ZM9.99996 12.5C10.6944 12.5 11.2847 12.2569 11.7708 11.7708C12.2569 11.2847 12.5 10.6944 12.5 10C12.5 9.30556 12.2569 8.71528 11.7708 8.22917C11.2847 7.74306 10.6944 7.5 9.99996 7.5C9.30552 7.5 8.71524 7.74306 8.22913 8.22917C7.74302 8.71528 7.49996 9.30556 7.49996 10C7.49996 10.6944 7.74302 11.2847 8.22913 11.7708C8.71524 12.2569 9.30552 12.5 9.99996 12.5Z"
                  fill="black" />
              </svg>
              <p>company@gmail.com</p>
            </li>

            <li class="flex space-x-2 items-center">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M5.51667 8.99167C6.71667 11.35 8.65 13.275 11.0083 14.4833L12.8417 12.65C13.0667 12.425 13.4 12.35 13.6917 12.45C14.625 12.7583 15.6333 12.925 16.6667 12.925C17.125 12.925 17.5 13.3 17.5 13.7583V16.6667C17.5 17.125 17.125 17.5 16.6667 17.5C8.84167 17.5 2.5 11.1583 2.5 3.33333C2.5 2.875 2.875 2.5 3.33333 2.5H6.25C6.70833 2.5 7.08333 2.875 7.08333 3.33333C7.08333 4.375 7.25 5.375 7.55833 6.30833C7.65 6.6 7.58333 6.925 7.35 7.15833L5.51667 8.99167Z"
                  fill="black" />
              </svg>
              <p>+27 (0)12 345 6789</p>
            </li>

            <li class="flex space-x-2 items-center">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M9.99996 1.66667C6.77496 1.66667 4.16663 4.27501 4.16663 7.5C4.16663 11.875 9.99996 18.3333 9.99996 18.3333C9.99996 18.3333 15.8333 11.875 15.8333 7.5C15.8333 4.27501 13.225 1.66667 9.99996 1.66667ZM5.83329 7.5C5.83329 5.20001 7.69996 3.33334 9.99996 3.33334C12.3 3.33334 14.1666 5.20001 14.1666 7.5C14.1666 9.9 11.7666 13.4917 9.99996 15.7333C8.26663 13.5083 5.83329 9.875 5.83329 7.5Z"
                  fill="black" />
                <path
                  d="M9.99996 9.58334C11.1506 9.58334 12.0833 8.6506 12.0833 7.50001C12.0833 6.34941 11.1506 5.41667 9.99996 5.41667C8.84937 5.41667 7.91663 6.34941 7.91663 7.50001C7.91663 8.6506 8.84937 9.58334 9.99996 9.58334Z"
                  fill="black" />
              </svg>

              <p>123 Lorem road
                Ipsum</p>
            </li>

          </ul>

        </div>

      </div>

      <!-- <div v-if="submitted">
        <h3>Thank you, {{ name }}!</h3>
        <p>We'll contact you at {{ email }} or {{ phone }} ASAP.</p>
        <p>Your message:</p>
        <p>{{ message }}</p>
      </div>
    </div> -->
      <!-- End of Text Box -->
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Form',
    props: {
      msg: String
    },
    data() {
      return {
        name: '',
        email: '',
        phone: '',
        message: '',
        nameError: '',
        emailError: '',
        phoneError: '',
        messageError: '',
        submitted: false
      }
    },
    methods: {
      validateForm() {
        this.nameError = this.name.length > 0 ? '' : 'Name is required'
        this.emailError = /\S+@\S+\.\S+/.test(this.email) ? '' : 'Email is invalid'
        this.phoneError = this.phone.length > 0 ? '' : 'Phone number is required'
        this.messageError = this.message.length > 0 ? '' : 'Message is required'

        return (
          this.nameError === '' &&
          this.emailError === '' &&
          this.phoneError === '' &&
          this.messageError === ''
        )
      },
      submitForm() {
        // if (this.validateForm()) {
        //   Send form data to PHP script for processing
        //   axios.post('/process_form.php', {
        //     name: this.name,
        //     email: this.email,
        //     phone: this.phone,
        //     message: this.message
        //   });
        // }

        console.log('Name:', this.name);
        console.log('Email:', this.email);
        console.log('Phone:', this.phone);
        console.log('Message:', this.message);
        this.submitted = true;

        this.name = '';
      this.email = '';
      this.phone = '';
      this.message = '';
      this.submitted = false;
      },
    }
  };
</script>

<style scoped lang="scss">
  #container {
    height: auto;

    // Start of Form styling
    form {
      background-color: rgba($color: #FFDB58, $alpha: 1.0);
      width: 95%;
      margin-inline: auto;
      height: auto;
      box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);

      @media (max-width:1023px) {
        width: 75%;
      }

      @media (max-width:767px) {
        width: 370px;
      }

      input,
      textarea {
        width: 75%;
        background: rgba($color: #ffffff, $alpha: .75);
        box-shadow: inset 0px 4px 4px rgba(0, 0, 0, 0.25);
        font-family: 'Archivo', sans-serif;

        &:focus {
          outline: none;
        }
      }

      button {
        width: 45%;
        font-family: 'Archivo', sans-serif;
        transition: ease all .2s;

        &:hover {
          box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
          transition: ease all .2s;
        }

        &:focus {
          outline: none;
        }
      }
    }

    // End of Form styling

    // Start of Text Box styling
    #text {
      width: 80%;
      display: grid;
      justify-self: center;
      box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);

      h2 {
        font-family: 'Poppins', sans-serif;
        color: #B2AC88;
      }

      p {
        font-family: 'Archivo', sans-serif;
        font-size: 16px;
      }

      h3 {
        font-family: 'Poppins', sans-serif;
        font-size: 32px;
        color: #B2AC88;
      }
    }

    // End of Text Box styling
  }
</style>