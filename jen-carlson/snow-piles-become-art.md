---
author: Jen Carlson
date: December 30, 2010  4:10 PM
title: Snow Piles Become Art
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
background: url('/web/20110226115337im_/http://gothamist.com/labs/images/progress.gif') center center no-repeat;
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





    <img src="https://web.archive.org/web/20110226115337im_/http://gothamist.com/assets_c/2010/12/snowdrawing1210-thumb-76x76-585621.jpg" title="" id="photo_1" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":1, "image": "https://web.archive.org/web/20110226115337/http://gothamist.com/upload/2010/12/snowdrawing1210.jpg", "caption": "", "credit":""};
        galleryObj['photo_1'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110226115337im_/http://gothamist.com/assets_c/2010/12/2snowdrawing1210-thumb-76x76-585619.jpg" title="" id="photo_2" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":2, "image": "https://web.archive.org/web/20110226115337/http://gothamist.com/upload/2010/12/2snowdrawing1210.jpg", "caption": "", "credit":""};
        galleryObj['photo_2'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110226115337im_/http://gothamist.com/assets_c/2010/12/4snowdrawing1210-thumb-76x76-585620.jpg" title="" id="photo_3" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":3, "image": "https://web.archive.org/web/20110226115337/http://gothamist.com/upload/2010/12/4snowdrawing1210.jpg", "caption": "", "credit":""};
        galleryObj['photo_3'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110226115337im_/http://gothamist.com/assets_c/2010/12/5snowdrawing1210-thumb-76x76-585622.jpg" title="" id="photo_4" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":4, "image": "https://web.archive.org/web/20110226115337/http://gothamist.com/upload/2010/12/5snowdrawing1210.jpg", "caption": "", "credit":""};
        galleryObj['photo_4'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110226115337im_/http://gothamist.com/assets_c/2010/12/3snowdrawing1210-thumb-76x76-585618.jpg" title="" id="photo_5" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":5, "image": "https://web.archive.org/web/20110226115337/http://gothamist.com/upload/2010/12/3snowdrawing1210.jpg", "caption": "", "credit":""};
        galleryObj['photo_5'] = photo;
    </script>
    <!--
    
    -->
    


</div></div><p>Brooklyn artist <a href="https://web.archive.org/web/20110226115337/http://www.michaeldarthur.com/">Michael Arthur</a> was yet another local to get artistic inspiration from the blizzard, he says he &quot;took a bunch of pics and then loaded them in to the brushes program on my iPad and drew on top of them. Turns out snow makes pretty good paper.&quot; Check it out:</p>

<p><iframe title="YouTube video player" class="youtube-player" type="text/html" width="640" height="510" src="https://web.archive.org/web/20110226115337if_/http://www.youtube.com/embed/hNc2k8U6PQE" frameborder="0"></iframe></p>

<p>Speaking of snow creativity... are people moving past the snowman? We haven&apos;t spotted too many out there.</p>