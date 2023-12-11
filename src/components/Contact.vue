<template>
  <div id="contact">
    <div class="container">
      <div class="row">
     <div class="boxT">
       <div class="contact-left">
         <h1 class="subtitle">Contact Me</h1>
         <p><i class="fa-solid fa-envelope"></i>shakirayoubbhat@gmail.com</p>
         <p><i class="fa-solid fa-phone"></i>+91 7006354926</p>
         <div class="social-icons">
           <a target="_blank" href="https://https://github.com/shakirayoub123.com/TahirAli32"><i
               class="fa-brands fa-github"></i></a>
           <a target="_blank" href="https://www.linkedin.com/in/shakir-ayoub-412a30147/"><i
               class="fa-brands fa-linkedin"></i></a>
           <a target="_blank" href="https://stackoverflow.com/users/18450548/shakir-ayoub"><i
               class="fa-brands fa-stack-overflow"></i></a>
           <a target="_blank" href="https://www.hackerrank.com/shakirayoubbhat?hr_r=1"><i
               class="fa-brands fa-hackerrank"></i></a>
         </div>
         <a href="https://drive.google.com/file/d/1vJOoI3a4HNU0LGvhnmZHYkf1SaooWxny/view?usp=drive_link"
            target="_blank" class="btn btn2 resume">Resume <i class="fa-solid fa-file"></i></a>
       </div>
       <!--              2-->
       <div class="contact-right ml-2">
         <form @submit.prevent="handleSubmit()" name="contactForm">
           <input type="text" name="name" placeholder="Your Full Name" required>
           <input type="email" name="email" placeholder="Your Email" required>
           <textarea name="message" rows="6" placeholder="Your Message" required></textarea>
           <button class="btn btn2" type="submit">Send Message</button>
         </form>
         <div class="confirmMessage none" id="confirmation">
           <h2>Message Sent Successfully</h2>
         </div>
       </div>
     </div>
      </div>
    </div>
    <div class="copyright">
      <p>Portfolio of <span>Shakir Ayoub</span> | Copyright {{ currentYear }}</p>
    </div>
  </div>
</template>


<script>
  import { collection, addDoc, Timestamp } from 'firebase/firestore'
  import { db } from '../firebase'

  export default {
  // Your existing component setup

  methods: {
  async handleSubmit() {
  event.preventDefault();
  let form = document.forms['contactForm']
  let confirmation = document.getElementById("confirmation")
  let name = form[0].value
  let email = form[1].value
  let message = form[2].value

  try {
  // Save form data to Firestore
  await addDoc(collection(db, "portfolioContact"), { name, email, message, datetime: Timestamp.now() })

  // Reset form and show success message
  form.reset()
  confirmation.classList.remove("none")
  form.classList.add("none")

  setTimeout(() => {
  confirmation.classList.add("none")
  form.classList.remove("none")
}, 3000)
} catch (error) {
  console.error("Error submitting form:", error)
  // Handle error, show error message, etc.
}
}
}
}
</script>

<style scoped>
.boxT{
  display: flex;
}
.btn2:hover {
  box-shadow: 0 0 10px 5px rgba(255, 0, 0, 0.7), 0 0 10px 10px rgba(255, 165, 0, 0.7), 0 0 30px 15px rgba(255, 255, 0, 0.7);
  background-color: rgba(255, 0, 0, 0.5); /* Optional background color for added effect */
}

.none {
  display: none;
}

.contact-left {
  flex-basis: 35%;
  margin-right: 20px;
}

.contact-left p {
  margin-top: 30px;
}

.contact-right {
  flex-basis: 65%;
}

.contact-left p i {
  color: #ff004f;
  margin-right: 15px;
  font-size: 25px;
}

.social-icons {
  margin-top: 30px;
}

.social-icons a {
  font-size: 30px;
  margin-right: 35px;
  display: inline-block;
  color: #ababab;
  transition: all .5s;
}

.social-icons a:hover {
  color: #ff004f;
  transform: translateY(-5px);
}

.btn2 {
  display: inline-block;
  background-color: #ff004f;
}

.contact-right form {
  width: 97%;
}

.confirmMessage h2 {
  color: #ff004f;
}

.confirmMessage p {
  color: #fff;
}

form input,
form textarea {
  width: 100%;
  border: none;
  outline: none;
  background: #262626;
  padding: 15px;
  margin: 15px 0;
  color: #fff;
  font-size: 18px;
  border-radius: 6px;
}

form .btn2 {
  padding: 14px 60px;
  font-size: 18px;
  margin: 20px 0;
  cursor: pointer;
}

.copyright p {
  text-align: center;
  padding: 20px 0;
  background: #262626;
  font-weight: 400;
  font-size: 15px;
  margin-top: 20px;
  letter-spacing: .08rem;
}

.copyright span {
  color: #ff004f
}

@media only screen and (max-width: 600px) {
  .row {
    display: block;
  }

  .contact-left {
    margin-bottom: 40px;
  }

  .contact-left h1 {
    font-size: 50px;
  }
}</style>