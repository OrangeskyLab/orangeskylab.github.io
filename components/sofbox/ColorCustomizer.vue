<template>
  <div class="iq-customizer" :class="panel">
    <div class="buy-button">
      <a class="opener" href="javascript:void(0)" @click="toggle()"><i class="fa fa-spinner fa-spin" /></a>
    </div>
    <div class="clearfix content-chooser">
      <ul class="iq-colorChange clearfix">
        <li v-for="(color,index) of colors"
            :key="index"
            :class="(color.selected) ? 'selected' : ''"
            :style="'backgroundColor:'+color.code"
            @click="styleChange(color)"></li>
      </ul>
    </div>
  </div>
</template>
<script>
const $ = require('jquery')
export default {
  name: 'ColorCustomizer',
  data () {
    return {
      panel: 'closed',
      colors: [
        { code: '#f46d4f', rgb: '244, 109, 79', image: 'color-1', selected: 1 },
        { code: '#4ac4f3', rgb: '74, 196, 243', image: 'color-2', selected: 0 },
      ]
    }
  },
  methods: {
    toggle () {
      this.style_switcher = $('.iq-customizer')
      const panelWidth = this.style_switcher.outerWidth(true)
      if (this.panel === 'closed') {
        this.panel = 'opened'
        this.style_switcher.animate({ right: '0px' })
      } else {
        this.panel = 'closed'
        this.style_switcher.animate({ right: '-' + panelWidth })
      }
    },
    styleChange (color) {
      document.documentElement.style.setProperty('--primary-theme-color', color.code)
      document.documentElement.style.setProperty('--primary-rgb-theme-color', color.rgb)
      $('#logo_img').attr('src', require('assets/images/color-customizer/' + color.image + '.png'))
      this.colors.filter(item => item.selected === 1)[0].selected = 0
      // const i = this.colors.indexOf(color)
      // this.colors[i].selected = 1
    }
  }
}
</script>
