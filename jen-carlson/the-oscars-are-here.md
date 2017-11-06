---
author: Jen Carlson
date: February 27, 2011  7:40 PM
title: The Oscars Are Here
---

	      <div class="galleryEase" id="gallery-0">

<!-- gallery js -->
<script type="text/javascript"> 

var galleryObj = new Object();
var clicks = 0;
var swapAdEvery = 3;

function gallerySwap(photoObj) {
    clicks++;
    // function to swap in the image, caption, title, credit
    var info = '';
    if (photoObj.title && photoObj.title.length > 0) {
        info += "<strong>" + photoObj.title + "</strong>";
    }
    
    if (photoObj.caption && photoObj.caption.length > 0) {
        info += photoObj.caption;
    }
    
    if (photoObj.credit && photoObj.credit.length > 0) {
        info += "(<em>" + photoObj.credit + "</em>)";        
    }
    
    if (clicks % swapAdEvery == 0) {
        adSwap();
    }
    
    document.location.hash = 'photo-' + photoObj.id;
    
    $('#galleryImg')[0].src = photoObj.image; // .attr('src', photoObj.image);
    $('.galleyEaseInfo').html(info);
}

function adSwap() {
    $('.item-skyscraper').each(function() {
        $(this).find('iframe').each(function() {
            $(this).attr('src', $(this).attr('src') ); // hacky!
        });
    });
}

$(document).ready(function(){
    // check location hash
    var c = 0;
    var hash = document.location.hash.match(/photo-(\d+)/);
    if (hash && hash.length > 0) {
        c = hash[1];
        c--;
    }

    // populate the initial image
//    $('.galleryEaseThumb').addClass('galleryEaseActiveThumb').removeClass('galleryEaseThumb');
    var rel = $('.galleryEaseActiveThumb:eq(' + c + ')').attr('id');
    $('.galleryEaseActiveThumb:eq(' + c + ')').removeClass('galleryEaseActiveThumb').addClass('galleryEaseThumb');
    gallerySwap(galleryObj[rel]);
    
    
    
    $('.galleryEaseActiveThumb').live('click', function() {
        var photoObj = galleryObj[$(this).attr('id')];
        
        gallerySwap(photoObj);
        $('.galleryEaseThumb').addClass('galleryEaseActiveThumb').removeClass('galleryEaseThumb');
        $(this).removeClass('galleryEaseActiveThumb').addClass('galleryEaseThumb');
    });
    
    $('.galleryEaseNext, #galleryImg').click(function() {
        var idNum = $('.galleryEaseThumb').attr('id').match(/\d+/)[0];
        idNum = parseInt(idNum);
        if ($('#photo_' + (idNum+1)).length <= 0) { // we're at the end, roll around
            var photoObj = galleryObj[$('.galleryEaseActiveThumb:first').attr('id')];
            
            gallerySwap(photoObj);
        
            $('.galleryEaseThumb').addClass('galleryEaseActiveThumb').removeClass('galleryEaseThumb');
            $('.galleryEaseActiveThumb:first').addClass('galleryEaseThumb').removeClass('galleryEaseActiveThumb');
            
        } else {
            var id = $('.galleryEaseThumb').attr('id').match(/\d+/);
            id = id[0];
            id++;

            var photoObj = galleryObj['photo_' + id];
            
            gallerySwap(photoObj);
            
            $('.galleryEaseThumb').removeClass('galleryEaseThumb').addClass('galleryEaseActiveThumb');
            $('#photo_' + id).addClass('galleryEaseThumb').removeClass('galleryEaseActiveThumb');
 
        }
        
    });
    
    $('.galleryEasePrev').click(function() {
        if ($('.galleryEaseThumb').is(":first-child")) { // we're at the end, roll around
            var photoObj = galleryObj[$('.galleryEaseActiveThumb:last').attr('id')];
            
            gallerySwap(photoObj);
        
            $('.galleryEaseThumb').addClass('galleryEaseActiveThumb').removeClass('galleryEaseThumb');
            $('.galleryEaseActiveThumb:last').addClass('galleryEaseThumb').removeClass('galleryEaseActiveThumb');
            
        } else { 
            var photoObj = galleryObj[$('.galleryEaseThumb').prev().attr('id')];
            gallerySwap(photoObj);
            
            $('.galleryEaseThumb').prev().addClass('galleryEaseThumb').removeClass('galleryEaseActiveThumb');
            $('.galleryEaseThumb:last').addClass('galleryEaseActiveThumb').removeClass('galleryEaseThumb');
 
        }
    });
});
 
 
</script>
<!-- end gallery js -->

<style type="text/css">
#imgContainer {
min-height: 300px;
min-width: 300px;
background: url('/web/20110228114010im_/http://gothamist.com/labs/images/progress.gif') center center no-repeat;
}
</style>

<!--start of gallery code-->
<a name="gallery"></a>
<div class="galleryEaseDisplayed">
<div id="imgContainer">
    <img id="galleryImg">
</div>
<div class="galleyEaseInfo"></div>
<div class="galleryEaseNext"></div>
<div class="galleryEasePrev"></div>
</div>
<div class="galleryEaseThumbs">





    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/5oscars0211-thumb-76x76-601865.jpg" title="" id="photo_1" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":1, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/5oscars0211.jpg", "caption": "Anne Hathaway", "credit":""};
        galleryObj['photo_1'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/7oscars0211-thumb-76x76-601903.jpg" title="" id="photo_2" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":2, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/7oscars0211.jpg", "caption": "Scarlett Johansson", "credit":""};
        galleryObj['photo_2'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/3oscars0211-thumb-76x76-601857.jpg" title="" id="photo_3" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":3, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/3oscars0211.jpg", "caption": "Melissa Leo and Hailee Steinfeld, both up for Actress in a Supporting Role", "credit":""};
        galleryObj['photo_3'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/8oscars0211-thumb-76x76-601902.jpg" title="" id="photo_4" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":4, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/8oscars0211.jpg", "caption": "Jennifer Hudson and Cate Blanchett", "credit":""};
        galleryObj['photo_4'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/6oscars0211-thumb-76x76-601866.jpg" title="" id="photo_5" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":5, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/6oscars0211.jpg", "caption": "What are you guys doing here? (Russell Brand and Mandy Moore)", "credit":""};
        galleryObj['photo_5'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/4oscars0211-thumb-76x76-601858.jpg" title="" id="photo_6" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":6, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/4oscars0211.jpg", "caption": "Michelle Williams and Jennifer Lawrence, both up for Actress in a Leading Role", "credit":""};
        galleryObj['photo_6'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/9oscars0211-thumb-76x76-601904.jpg" title="" id="photo_7" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":7, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/attachments/arts_jen/9oscars0211.jpg", "caption": "Marisa Tomei and Sharon Stone", "credit":""};
        galleryObj['photo_7'] = photo;
    </script>
    <!--
    
    -->
    <br>

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/oscars022711-thumb-76x76-601849.jpg" title="" id="photo_8" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":8, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/attachments/arts_jen/oscars022711.jpg", "caption": "", "credit":""};
        galleryObj['photo_8'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/2oscars022711-thumb-76x76-601856.jpg" title="" id="photo_9" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":9, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/2oscars022711.jpg", "caption": "Wolfgang Puck... trying to outdo Lady Gaga?", "credit":""};
        galleryObj['photo_9'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/10oscars0211-thumb-76x76-601906.jpg" title="" id="photo_10" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":10, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/10oscars0211.jpg", "caption": "Keith Urban, Nicole Kidman, Halle Berry", "credit":""};
        galleryObj['photo_10'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/11oscars0211-thumb-76x76-601908.jpg" title="" id="photo_11" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":11, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/11oscars0211.jpg", "caption": "Colin Firth and wife, Javier Bardem and Penelope Cruz", "credit":""};
        galleryObj['photo_11'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/13oscars0211-thumb-76x76-601909.jpg" title="" id="photo_12" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":12, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/13oscars0211.jpg", "caption": "Day & Night: Gwyneth Paltrow and Helena Bonham Carter", "credit":""};
        galleryObj['photo_12'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/14oscars0211-thumb-76x76-601910.jpg" title="" id="photo_13" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":13, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/14oscars0211.jpg", "caption": "Hillary Swank and Sandra Bullock", "credit":""};
        galleryObj['photo_13'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/15oscars0211-thumb-76x76-601911.jpg" title="" id="photo_14" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":14, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/15oscars0211.jpg", "caption": "Amy Adams and Reese Witherspoon", "credit":""};
        galleryObj['photo_14'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/16oscars0211-thumb-76x76-601912.jpg" title="" id="photo_15" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":15, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/16oscars0211.jpg", "caption": "Mila Kunis and a pregnant Natalie Portman", "credit":""};
        galleryObj['photo_15'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110228114010im_/http://gothamist.com/assets_c/2011/02/17oscars0211-thumb-76x76-601913.jpg" title="" id="photo_16" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":16, "image": "https://web.archive.org/web/20110228114010/http://gothamist.com/upload/2011/02/17oscars0211.jpg", "caption": "Christian Bale and his wife, Jesse Eisenberg", "credit":""};
        galleryObj['photo_16'] = photo;
    </script>
    <!--
    
    -->
    


</div></div><p>The 83rd Annual Academy Awards will be starting shortly, and we&apos;ll be getting some photos together of the red carpet arrivals (so check back here if you want to see the best and the worst). Host James Franco (who is sharing his duties tonight with Anne Hathaway) says he&apos;ll be <a href="https://web.archive.org/web/20110228114010/http://twitter.com/jamesfranco">Tweeting</a> from the event, and just posted this message from his suite:</p>

<center><object width="480" height="270"><param name="movie" value="http://media.whosay.com/public/video-player/20101221/player.swf?v_url=http%3A%2F%2Fmedia.whosay.com%2F13990%2F13990_480.flv&amp;tracker=UA-12028902-1&amp;videoId=13990&amp;viewmore=http%3A%2F%2Fwww.whosay.com%2Fjamesfranco%2Fvideos&amp;flipVideo=false&amp;autoplay=false"><param name="allowFullScreen" value="true"><param name="allowscriptaccess" value="never"><embed src="https://web.archive.org/web/20110228114010oe_/http://media.whosay.com/public/video-player/20101221/player.swf?v_url=http%3A%2F%2Fmedia.whosay.com%2F13990%2F13990_480.flv&amp;tracker=UA-12028902-1&amp;videoId=13990&amp;viewmore=http%3A%2F%2Fwww.whosay.com%2Fjamesfranco%2Fvideos&amp;flipVideo=false&amp;autoplay=false" type="application/x-shockwave-flash" allowscriptaccess="never" allowfullscreen="true" width="480" height="270"></object></center>

<p>Allegedly these are the &quot;most interactive&quot; the Oscars have gotten&#x2014;more on that <a href="https://web.archive.org/web/20110228114010/http://oscar.go.com/">here</a>. We&apos;ll be posting a full recap later tonight.</p>