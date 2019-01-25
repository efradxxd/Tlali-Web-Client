<template>
  <div>
    <Sidebar />
    <Header />
    <nuxt/>
  </div>
</template>

<script>
import Sidebar from '@/components/Sidebar'
import Header from '@/components/Header'
export default {
  components: {
    Sidebar,
    Header
  }
}
</script>
