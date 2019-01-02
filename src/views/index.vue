<template>
  <div class="index" id='index'>
  	<mhead></mhead>
    <div class='index-content clearfix'>
    	<transition name='CutIn-from-left' appear>
    		<aside>
          <div class='logo'>
            <img src='../assets/logo.png'>
          </div>
          <h2>{{ name }}</h2>
          <div class='icon'>
            <div class='PopOut'>
              <div :class='{show: Icon_Show.Icon1}'>
                <i></i>
                <span>Github</span>
              </div>
              <div :class='{show: Icon_Show.Icon2}'>
                <i></i>
                <span>微博</span>
              </div>
              <div :class='{show: Icon_Show.Icon3}'>
                <i></i>
                <span>QQ</span>
              </div>
              <div :class='{show: Icon_Show.Icon4}'>
                <i></i>
                <span>微信</span>
              </div>
            </div>
            <a href='' @mouseenter='IconShow(1)' @mouseleave='IconClear(1)'>
              <i class='iconfont'>&#xe7ab;</i>
            </a>
            <a href='' @mouseenter='IconShow(2)' @mouseleave='IconClear(2)'>
              <i class='iconfont'>&#xe75a;</i>
            </a>
            <a href='' @mouseenter='IconShow(3)' @mouseleave='IconClear(3)'>
              <i class='iconfont'>&#xe600;</i>
            </a>
            <a href='' @mouseenter='IconShow(4)' @mouseleave='IconClear(4)'>
              <i class='iconfont'>&#xe610;</i>
            </a>
          </div>
          <p>{{ signature }}</p>
          <textarea v-model='signature'></textarea>
        </aside>
    	</transition>
    	<transition name='CutIn-from-bottom' appear>
    		<div></div>
    	</transition>
  		<transition name='CutIn-from-right' appear>
  			<aside></aside>
  		</transition>
  	</div>
  </div>
</template>

<script>
// @ is an alias to /src
import mhead from '@/components/mhead'

export default {
  name: 'index',
  data: function () {
    return {
      name: 'X_X >_<',
      Icon_Show: {
        Icon1: false,
        Icon2: false,
        Icon3: false,
        Icon4: false
      },
      signature: ''
    }
  },
  methods: {
    IconShow: function (index) {
      this.Icon_Show['Icon' + index] = true
    },
    IconClear: function (index) {
      this.Icon_Show['Icon' + index] = false
    },
    pageInit: function () {
      let t = this
      t.axios({
        method: 'GET',
        url: '',
        params: {}
      })
    }
  },
  mounted: function () {
    let t = this
    t.pageInit()
  },
  components: {
  	mhead
  }
}
</script>
