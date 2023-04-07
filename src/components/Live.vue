<template>
  <div class="live">
    <p class="header">婚礼邀请</p>
    <img src="~@/assets/images/hands.png" class="hands" />
    <div>
      <p>
        记得两年前的那个国庆节，我和小祝相识了。当时，小祝穿着一件黑色大衣，微微一笑，就深深地吸引了我的眼球，
        当时我就有了一种奇妙的感觉：这个女孩就是我一直在寻找的那个人。<br /><br />
        自那以后，我和小祝开始了漫长的恋爱之路。我们一起去骑车，一起看爬山，一起尝试各种美食。我们经历了许多甜蜜的时刻，也经历了一些挫折和磨合。但是，我们从来没有放弃过对彼此的爱和信任。<br /><br />
        现在，我们终于要步入婚姻的殿堂了。我感谢上天给了我这么一个美丽、聪明、善良的女孩，也感谢小祝一直以来的陪伴和支持。我们的婚礼将带领我们走向人生的新篇章。<br />
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Live',
};
</script>

<style lang="scss" scoped>
.live {
  padding-top: 4px;
  padding-bottom: 68px;
  padding-left: $padding-vertical;
  padding-right: $padding-vertical;
  text-align: center;
  .hands {
    width: 75px;
    margin-bottom: 16px;
  }
  p {
    margin-bottom: 16px;
    line-height: 24px;
    &.desc {
      color: #295238;
      font-size: 10px;
      opacity: 0.6;
      margin-bottom: 36px;
    }
    &.header {
      margin-top: 30px;
      font-size: 24px;
      color: #295238;
    }
    &:last-child {
      margin-bottom: 40px;
    }
  }
}
</style>
