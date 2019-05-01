<template>
  <div class="hello">
  <div class="container">
  <b-list-group horizontal>
    <b-list-group-item><b-form-checkbox>本店</b-form-checkbox></b-list-group-item>
    <b-list-group-item><b-form-checkbox>楽天</b-form-checkbox></b-list-group-item>
    <b-list-group-item><b-form-checkbox>Yahoo!</b-form-checkbox></b-list-group-item>
    <b-list-group-item><b-form-checkbox>Amazon</b-form-checkbox></b-list-group-item>
    <b-list-group-item><b-form-checkbox>Wowma!</b-form-checkbox></b-list-group-item>
    <b-list-group-item><b-form-checkbox>ポンパレ</b-form-checkbox></b-list-group-item>
    <b-list-group-item><b-form-checkbox>Qoo10</b-form-checkbox></b-list-group-item>
  </b-list-group>
  </div>
        <p class="text-right">検索 <input size="sm" class="mr-sm-2" type="text" v-model="keyword" placeholder="商品名,商品情報,etc..."></p>

<table class="table table-striped table-bordered table-hover">
<tr><th>商品番号</th><th>商品名</th><th>価格</th><th>限界利益</th></tr>
<tr v-for="item in filteredItem">
<td v-text="item.商品番号"></td><td v-text="item.itemName" class="text-left"></td><td v-text="item.価格"></td><td v-text="item.限界利益"></td>
</tr>
</table>
  </div>
</template>

<script>
export default {
  name: 'ItemMaster',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      keyword: '',
              items: [
          { 商品番号: 'mf-001', itemName: 'マリアージュフレール アールグレイインペリアル', 価格: 3200, 限界利益: 600, },
          { 商品番号: 'mf-002', itemName: 'マリアージュフレール ボレロ', 価格: 3000, 限界利益: 720, },
          { 商品番号: 'mf-003', itemName: 'マリアージュフレール ウェディングインペリアル', 価格: 3200, 限界利益: 650, },
          { 商品番号: 'mf-004', itemName: 'マリアージュフレール マルコポーロ', 価格: 2900, 限界利益: 620, },
          { 商品番号: 'fm-001', itemName: 'フォートナム&メイソン アールグレイクラシック', 価格: 3240, 限界利益: 400, },
          { 商品番号: 'fm-002', itemName: 'フォートナム&メイソン ダージリンBOP', 価格: 3240, 限界利益: 400, },
          { 商品番号: 'fm-003', itemName: 'フォートナム&メイソン ロイヤルブレンド', 価格: 3240, 限界利益: 400, },
          { 商品番号: 'fm-004', itemName: 'フォートナム&メイソン スモーキーアールグレイ', 価格: 3240, 限界利益: 400, },
          { 商品番号: 'th-001', itemName: 'テイラーズオブハロゲイト アールグレイ', 価格: 3240, 限界利益: 500, },
          { 商品番号: 'th-002', itemName: 'テイラーズオブハロゲイト クアズル', 価格: 3240, 限界利益: 620, },
          { 商品番号: 'th-003', itemName: 'テイラーズオブハロゲイト イングリッシュブレックファースト', 価格: 3360, 限界利益: 600, },
          { 商品番号: 'th-004', itemName: 'テイラーズオブハロゲイト ティールームブレンド', 価格: 3564, 限界利益: 600, },
        ]
    }
  },
  computed: {
    filteredItem: function() {
      var items = [];
      for(var i in this.items) {
        var item = this.items[i];
        if(item.itemName.indexOf(this.keyword) !== -1) {
          items.push(item);
        }
      }
      return items;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
tr:hover {
  background: #fafafa;
}
th {
  background: #eee;
}
</style>
