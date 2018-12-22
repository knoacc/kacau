<style type="text/css">
        video {
  object-fit: fill;
}
    body{
      background-color:black;
    }
    #player{
      position: absolute;
      top: 0px;
      right: 0px;
      bottom: 0px;
      left: 0px;
      margin: auto;
      max-height: 100%;
      max-width: 100%;
    }
  </style>
<script src='//api.peer5.com/peer5.clappr.plugin.js'></script>
<script src='https://cdn.jsdelivr.net/clappr/latest/clappr.min.js' type='text/javascript'></script>
<script src='https://cdn.jsdelivr.net/clappr.level-selector/latest/level-selector.min.js' type='text/javascript'></script>
<div id='player'>
</div>
<script>
//<![CDATA[
function getQueryParam(param) {
var result =  window.location.search.match(new RegExp("(\\?|&)" + param + "(\\[\\])?=([^&]*)")); return result ? result[3] : false;}
var topVideo = getQueryParam("x");
var playerElement = document.getElementById("player");
var player = new Clappr.Player({height: "100%", width: "100%", watermark: "https://repo.istimiwir.host/img/logo.png", size: '300', margin: '500', position: 'top-right', top: '-1000px', plugins: {'core': [LevelSelector]}, hlsjsConfig: {xhrSetup: function(xhr, url) {xhr.withCredentials = false;}}, playbackConfig: {crossorigin: 'use-credentials'}}); player.attachTo(playerElement); 
player.load({source: topVideo, mimeType: 'application/x-mpegURL'});
player.play();
//]]>
</script>

<script>
  // Show loading animation.
  var playPromise = Clappr.Player();

  if (playPromise !== undefined) {
    playPromise.then(_ => {
      // Automatic playback started!
      // Show playing UI.
    })
    .catch(error => {
      // Auto-play was prevented
      // Show paused UI.
    });
  </script>
