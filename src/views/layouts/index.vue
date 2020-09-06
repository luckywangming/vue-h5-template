<template>
  <div class="app-container">
    <div class="layout-content">
      <keep-alive v-if="$route.meta.keepAlive">
        <router-view></router-view>
      </keep-alive>
      <router-view v-else></router-view>
    </div>
    <div class="layout-footer">
      <TabBar :data="tabbars" @change="handleChange" />
    </div>
  </div>
</template>

<script>
import TabBar from '@/components/TabBar'
export default {
  name: 'AppLayout',
  data() {
    return {
      tabbars: [
        {
          title: '首页',
          to: {
            name: 'Home'
          },
          icon: {
            active: require('@/assets/imgs/icon_home.png'),
            inactive: require('@/assets/imgs/icon_home_no.png'),
          }
        },
        {
          title: '巡检工单',
          to: {
            name: 'Order'
          },
          icon: {
            active: require('@/assets/imgs/icon_xj.png'),
            inactive: require('@/assets/imgs/icon_xj_no.png'),
          }
        },
        {
          title: '我的',
          to: {
            name: 'About'
          },
          icon: {
            active: require('@/assets/imgs/icon_me.png'),
            inactive: require('@/assets/imgs/icon_me_no.png'),
          }
        }
      ]
    }
  },
  components: {
    TabBar
  },
  methods: {
    handleChange(v) {
      console.log('tab value:', v)
    }
  }
}
</script>
