<template>
  <div class="absol">
    <!-- <Header /> -->
    <Head class="fixed" />
    <Nuxt class="bg-gray-50"/>
    <!-- <Footer /> -->
    <Foot />
  </div>
</template>

<style>
  @import url(../assets/css/fonts.css);
  .poppins{
    font-family: 'Poppins', 'Spoqa Han Sans', 'Inter';
  }
  .absol{
    position: relative;
  }
  .fixed{
    position: fixed;
  }
</style>

<script>
export default {
  head() {
    let productionScripts = []
    if (process.env.NODE_ENV === 'production') {
      productionScripts = [
        { hid: 'analytics', src: 'https://www.googletagmanager.com/gtag/js?id=G-78SE6PS7BD', defer: true },
        { hid: 'analytics-script', innerHTML: "window.dataLayer = window.dataLayer || []; function gtag(){dataLayer.push(arguments);} gtag('js', new Date()); gtag('config', 'G-78SE6PS7BD');", type: 'text/javascript' }
      ]
    }

    return {
      title: "GDSC CAU",
      script: [

      ].concat(productionScripts),
      // __dangerouslyDisableSanitizers: ['script']
      __dangerouslyDisableSanitizersByTagID: {
        'analytics-script': ['innerHTML']
      }
    }
  }
}
</script>