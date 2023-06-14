## Youtube api and vimeo api

 ```
 <script>
// lic inner video

// https://developers.google.com/youtube/iframe_api_reference

// global variable for the player
var player;

// this function gets called when API is ready to use
function onYouTubePlayerAPIReady() {
    // create the global player from the specific iframe (#video)
    player = new YT.Player('iframe-video', {
         playerVars: {
        'rel': 0,
        'modestbranding': 1,
        'controls': 1,
        'showinfo': 0

    },
        events: {
            // call this function when player is ready to use
            'onReady': onPlayerReady
        }
    });
}

function onPlayerReady(event) {
             jQuery('.ytp-large-play-button').remove();
  // bind events
  var overlay = document.getElementById("overlay");
  var videoicon = document.getElementById("video-icon");
  var videocontent = document.getElementById("video-content");

  var width = jQuery('body').width();
  if(width < 768){
     overlay.addEventListener("click", function() {
        player.playVideo();
        jQuery('.video-icon').hide();          
         overlay.remove();
      });
      videoicon.addEventListener("click", function() {
        player.playVideo();
        jQuery('.video-icon').hide();
        overlay.remove();  
      });
  }
  else
  { 

        overlay.addEventListener("click", function() {
        player.playVideo();
        jQuery('.video-icon').hide();
        jQuery('.video-content').hide();
        overlay.remove();
        // const yticon = document.getElementsByClassName("ytp-large-play-button");
        // yticon.remove();
       
          
      });
      videoicon.addEventListener("click", function() {
        player.playVideo();
        jQuery('.video-icon').hide();
        jQuery('.video-content').hide();
         overlay.remove();  
      });
        videocontent.addEventListener("click", function() {
        player.playVideo();
        jQuery('.video-icon').hide();
        jQuery('.video-content').hide();
         overlay.remove();  
      });
  }

  // var pauseButton = document.getElementById("iframe-video");
  // pauseButton.addEventListener("click", function() {
  //   // playButton.show();
  //   player.pauseVideo();
  //    jQuery('.video-icon').show();
  //   console.log('asasas');
  // });
  
}



// youtube end

// vimeo start
    const iframe = document.querySelector('iframe');
  if(iframe != null){
        var vimeosrc = iframe.src;
        vimeourl = 'vimeo.com';
        var match = vimeosrc.match(vimeourl);
        if(match == 'vimeo.com'){
            const player1 = new Vimeo.Player(iframe);
            var overlay = document.getElementById("overlay");
            var videoicon = document.getElementById("video-icon");
            var videocontent = document.getElementById("video-content");

            var width = jQuery('body').width();
            if(width < 768){
                overlay.addEventListener("click", function() {
                player1.play();
                jQuery('.video-icon').hide();   
                overlay.remove();       
              });
              videoicon.addEventListener("click", function() {
                player1.play();
                jQuery('.video-icon').hide();
                 overlay.remove();   
              });
            }
            else
            {   
                overlay.addEventListener("click", function() {
                player1.play();
                jQuery('.video-icon').hide();  
                jQuery('.video-content').hide();     
                 overlay.remove();     
              });
                videoicon.addEventListener("click", function() {
                player1.play();
                jQuery('.video-icon').hide();
                jQuery('.video-content').hide();
                 overlay.remove(); 
              });
                videocontent.addEventListener("click", function() {
                player1.play();
                jQuery('.video-icon').hide();
                jQuery('.video-content').hide();
                overlay.remove();
                });
            }    

        }
    }  
    // vimeo end   
    </script>
    ```
    
   
