<div :class="{hidden: toolbarHidden}">
  <div class="systemButton musicButton" 
    @click="track = getRandomTrack()" ><fa-icon icon="random"></fa-icon></div>
  <FlashCredit forceShow="true" class="FlashCredit" v-if="track" :trackIds="[track.directory]"/>
  <webview
    class="bandcamp" 
    allowtransparency 
    disablewebsecurity
    seamless
    :src="webviewTargetUrl"
    ref="webview"
    ></webview>
  <div class="systemButton musicButton" 
    @click="$archive.flags['BCToolbarShow'] = false" ><fa-icon icon="chevron-up"></fa-icon></div>
  <div v-if="$localData.settings.devMode" class="systemButton musicButton" 
    @click="webview.openDevTools()" ><fa-icon icon="mouse-pointer"></fa-icon></div>
</div>
