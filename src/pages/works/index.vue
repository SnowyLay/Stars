<template>
  <div>
  <i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>    
  </i-grid>  
  <i-panel :title="title_name">
    <view style="padding: 15px;">
     <i-card v-for="item in top" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
        <view slot="content">{{item.remark}}</view>
        <view slot="footer">{{item.time}}</view>
     </i-card>
    </view>
  </i-panel> 
  </div>
</template>

<script>
export default {
  data () {
    return {
      title_name: "热门作品",
      grids: [
        {title:"歌曲",image:"cloud://uniq-eylru.756e-uniq-eylru-1301004850/1.png"},
        {title:"影视",image:"cloud://uniq-eylru.756e-uniq-eylru-1301004850/2.png"},
        {title:"综艺",image:"cloud://uniq-eylru.756e-uniq-eylru-1301004850/3.png"},
        {title:"杂志",image:"cloud://uniq-eylru.756e-uniq-eylru-1301004850/4.png"}
      ],
      top: [
        {name:"Best Friend",time:"发行时间:2015-10-16",image:"cloud://uniq-eylru.756e-uniq-eylru-1301004850/BS.jpg",remark:"UNIQ出道一周年纪念单曲"},
        {name:"Falling in Love",time:"发行时间:2014-10-20",image:"cloud://uniq-eylru.756e-uniq-eylru-1301004850/FIL.jpg",remark:"韩国出道舞台演绎首支单曲《Falling In Love》"},
        {name:"抹去你的小伤心",time:"发行时间:2015-11-23",image:"cloud://uniq-eylru.756e-uniq-eylru-1301004850/MQN.jpg",remark:"美国派拉蒙动画电影《海绵宝宝》中国版主题曲"},
        {name:"My Dream",time:"发行时间:2016-03-24",image:"cloud://uniq-eylru.756e-uniq-eylru-1301004850/MD.jpg",remark:"电影《梦想合伙人》片尾曲"}
      ]
    }
  },


  methods: {
    goType(type){
      console.log(type)
      let url = '../list/main?type=' + type.title
      mpvue.navigateTo({ url })
    }
    },
   

  created () {
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
div >>> .split {
  margin-bottom: 10pt;
}
</style>
