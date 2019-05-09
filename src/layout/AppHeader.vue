<template>
  <header class="header-global">
    <base-nav v-for="menu in menus"
              :key="menu.type"
              :type="menu.type"
              effect="dark"
              title=""
              expand
              :content-id="`navbar-${menu.type}`">
    <div class="col-lg-12 col-sm-4">
      <base-input alternative placeholder="Search by ISBN" addon-right-icon="ni ni-zoom-split-in">
      </base-input>
    </div>
    </base-nav>
  </header>
</template>
<script>

import BaseNav from "@/components/BaseNav";
import Menu1 from "../views/components/Navigation/Menu1";

export default {
  components: {
    Menu1,
    BaseNav,
  },
  data() {
    return {
      menus: [
        { type: "default", menuComponent: Menu1 }
      ]
    };
  }
};
</script>
<style>
</style>
