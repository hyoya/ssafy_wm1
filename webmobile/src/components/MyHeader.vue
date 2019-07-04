<template>
  <v-layout>
    <v-flex column>
      <v-toolbar fixed style="background:#ff6783;">

        <v-btn icon to="/">🌺</v-btn>
        <v-toolbar-title class="white--text">HYOYA</v-toolbar-title>
        <v-icon v-on:click="AddBookmark">bookmark</v-icon>
        <v-spacer></v-spacer>

        <v-toolbar-items class="hidden-xs-only">
            <v-btn
            v-for="item in menu"
            :key="item.icon"
            :to="item.link"
            flat
            class="white--text"
            >{{ item.title }} </v-btn>
        </v-toolbar-items>

        <v-menu class="hidden-sm-and-up">
          <v-toolbar-side-icon slot ="activator" class="white--text"></v-toolbar-side-icon>
          <v-list>
            <v-list-tile v-for="item in menu" :key="item.icon" :to="item.link">
              <v-list-tile-content>
                <v-list-tile-title>
                  {{ item.title }}
                </v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list>
        </v-menu>

      </v-toolbar>
    </v-flex>
  </v-layout>

</template>

<script>
export default {
	name: 'MyHeader',
	props: {
	},
	data: () => ({
    menu : [
      {icon : 'home', title:'HOME', link:"/"},
      {icon : 'portfolio', title:'PORTFOLIO', link:"/portfolio"},
      {icon : 'post', title:'POST', link:"/post"},
      {icon : 'login', title:'LOGIN', link:"/login"},
    ],
  }),
  methods: {
 AddBookmark : function() {
   var url = this.location;
   var title = document.title;
   if (window.sidebar && window.sidebar.addPanel){ // Firefox
   window.sidebar.addPanel(sidebartitle, sidebarurl,"");
   alert("FF")
   }
   else if ( document.all ) { // IE Favorite
   window.external.AddFavorite(url, title);
   alert("IE")
   }
   else if (window.opera && window.print) {
   // do nothing
   alert("OPERA")
    }
   else if (navigator.appName=="Netscape") {
    alert((navigator.userAgent.toLowerCase().indexOf('mac') != -1 ? 'Cmd' : 'Ctrl') + '+D 키를 눌러 즐겨찾기에 등록하실 수 있습니다.');
  }
}
}
}
</script>
