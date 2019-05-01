<template>
<div>
  <b-navbar toggleable="md" type="dark" variant="info">
  <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>
  <b-navbar-brand href="#">Cancer - v0.0.1</b-navbar-brand>
  <b-collapse is-nav id="nav_collapse">
    <b-navbar-nav>
      <b-nav-item href="#">商品管理</b-nav-item>
      <b-nav-item href="#" disabled>日次決算</b-nav-item>
    </b-navbar-nav>

    <!-- Right aligned nav items -->
    <b-navbar-nav class="ml-auto">
      <b-nav-form>
        <b-form-input size="sm" class="mr-sm-2" type="text" placeholder="機能検索"/>
        <b-button size="sm" class="my-2 my-sm-0" type="submit">検索</b-button>
      </b-nav-form>

      <b-nav-item-dropdown text="設定" right>
        <b-dropdown-item href="#">EN</b-dropdown-item>
        <b-dropdown-item href="#">ES</b-dropdown-item>
        <b-dropdown-item href="#">RU</b-dropdown-item>
        <b-dropdown-item href="#">FA</b-dropdown-item>
      </b-nav-item-dropdown>

      <b-nav-item-dropdown right>
        <!-- Using button-content slot -->
        <template slot="button-content">
          <em>ユーザー</em>
        </template>
        <b-dropdown-item href="#">ユーザー管理</b-dropdown-item>
        <b-dropdown-item href="#">ログアウト</b-dropdown-item>
      </b-nav-item-dropdown>
    </b-navbar-nav>
  </b-collapse>
  </b-navbar>

  <div id="app">
    <ItemMaster/>
  </div></div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import ItemMaster from './components/ItemMaster'

export default {
  name: 'App',
  components: {
    ItemMaster
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
