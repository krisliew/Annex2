<template>
  <div>
    <Header />
    <About />
    <Service />
    <Contact />
  </div>
</template>

<script>
import Header from '~/components/Header'
import About from '~/components/About'
import Service from '~/components/Service'
import Contact from '~/components/Contact'

export default {
  components: {
    Header,
    About,
    Service,
    Contact,
  },
}
</script>
