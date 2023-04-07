<template>
  <div class="funding">
    <img src="~@/assets/images/flower.png" class="flower" />
    <h2 class="h2">
      尊敬的
      <div class="name">李毅大帝520</div>
    </h2>
    <p>
      我和小祝终于要结婚啦！在这个特殊的日子里，我们非常期待你的光临。<br />
      你的到来将使我们的婚礼更加完美，让我们的人生更加充实。我们很高兴邀请你参加我们的婚礼，我们相信你的到来将使这一天更加难忘。<br />
      感谢你的出席，我们相信这将是我们一生中非常难忘的时刻。<br />
      谢谢！<br />
      敬礼，<br />
      老王和小祝
    </p>
  </div>
</template>

<script>
export default {
  name: 'Divider',
  data() {
    return {
      name: '',
    };
  },
  created() {
    // this.name = window.location.query.name;
    console.log(decodeURI(window.location.search.slice(1)));
  },
};
</script>

<style lang="scss" scoped>
.funding {
  padding-top: 48px;
  padding-bottom: 72px;
  padding-left: $padding-vertical;
  padding-right: $padding-vertical;
  text-align: center;

  .flower {
    width: 70px;
    margin-bottom: 26px;
  }
  .h2 {
    font-size: 16px;
    font-weight: normal;
    margin-bottom: 24px;
    color: #295138;
    .name {
      display: inline-block;
      margin-left: 8px;
      min-width: 50px;
      border-bottom: 2px solid #295138;
      padding: 0 10px;
    }
  }
  p {
    margin-bottom: 32px;
    line-height: 24px;
    color: #202121;
  }
  .link {
    display: inline-block;
    margin-top: 24px;
    color: #295238;
  }
}
</style>
