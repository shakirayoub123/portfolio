<template>
    <Header />
    <About />
    <Services />
    <Portfolio />
    <Quotes />
    <Contact />
</template>

<script>
import Header from '../components/Header.vue'
import About from '../components/About.vue'
import Services from '../components/Services.vue'
import Portfolio from '../components/Portfolio.vue'
import Contact from '../components/Contact.vue'
import Quotes from "@/components/Quotes.vue";

export default {
  name: 'Home',
  components: {
    Quotes,
    Header,
    About,
    Services,
    Portfolio,
    Contact,
  }
}
</script>