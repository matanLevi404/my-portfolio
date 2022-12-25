<template>
  <section id="contact" class="contact-section section">
    <div class="container">
      <h2 class="title">Contact.</h2>
      <form class="form">
        <input type="text" placeholder="Enter Your Name" />
        <input type="text" placeholder="Enter Your Email" />
        <input type="text" placeholder="Enter Your Phone" />
        <!-- <input type="text" placeholder="Your Messege ..." /> -->
        <textarea
          name="message"
          rows="10"
          placeholder="Your Message ..."
        ></textarea>
        <Button
          text="Send Message Now"
          color="#161616"
          background="transparent"
          hoverBackground="#f7f7f7"
          borderColor="#cecece"
          hoverBorderColor="#333"
          borderPx="1px"
        />
      </form>
    </div>
  </section>
</template>

<script>
import Button from "./Button";

export default {
  name: "Contact",
  components: { Button },
  methods: {
    sendGmail() {
      Email.send({
        Host: "smtp.elasticemail.com",
        Username: "username",
        Password: "password",
        To: "them@website.com",
        From: "you@isp.com",
        Subject: "This is the subject",
        Body: "And this is the body",
      }).then((message) => alert(message));
    },
  },
};
</script>

<style scoped>
.contact-section {
  background-color: #f7f7f7;
  padding: 80px 0px;
}

.form {
  width: 75%;
  background-color: #fff;
  margin: 0 auto;
  padding: 50px;
}

input,
textarea {
  font-size: 15px;
  width: 100%;
  color: #161616;
  outline: none;
  border: none;
  padding: 20px 20px 20px 0px;
  margin-bottom: 15px;
  border-bottom: 1px solid #7777;
}

textarea {
  resize: none;
  height: 230px;
}

button {
  font-weight: 400;
  margin-top: 30px;
}

@media (max-width: 992px) {
  .form {
    width: 100%;
  }

  h2 {
    font-size: 35px;
  }
}
</style>
