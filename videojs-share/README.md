Here is a demo of Limelight HTML player using videojs-share plugin which allows user to copy video url and share it through some of their favorite social network apps.

Additional information about the plugin and its configuration can be found here:
    https://www.npmjs.com/package/videojs-share

Steps:
  1. On your webpage, paste the limelight player embed
  2. Add the videojs-share CSS to your page
  3. In your limelightPlayerCallback function on playerload event
      - get the videojs reference from limelight player
          vjs = LimelightPlayer.doGetVjs()
      - copy existing videojs object if any and update with limelight's vjs one
          var originalVideojs = window.videojs; 
          window.videojs = vjs
      - now load the videojs-share plugin
          loadScriptAsync('videojs-share.js', call-back-function()
      - in your call-back function()
          once the js file is loaded it autoregister the share plugin with the videojs instance
  4. Initialize the plugin with some social sharing information in JSON format
      shareOptions
        URL to be copied and shared
        choose the social sharing apps you want to share to
  5. invoke the plugin through player instance
      LimelightPlayer.doGetVjsPlayer().share(shareOptions);
  6. Make sure to have the correct playerId at all its references

