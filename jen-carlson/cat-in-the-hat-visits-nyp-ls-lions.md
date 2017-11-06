---
author: Jen Carlson
date: February 24, 2011  2:54 PM
title: Cat In The Hat Visits NYPL's Lions
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
background: url('/web/20110226111728im_/http://gothamist.com/labs/images/progress.gif') center center no-repeat;
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





    <img src="https://web.archive.org/web/20110226111728im_/http://gothamist.com/assets_c/2011/02/suessnypl02211-thumb-76x76-601035.jpg" title="" id="photo_1" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":1, "image": "https://web.archive.org/web/20110226111728/http://gothamist.com/attachments/arts_jen/suessnypl02211.jpg", "caption": "The Cat in the Hat at the NYPL!", "credit":"Courtesy of the <a href=\"http://nypl.org\">New York Public Library</a>"};
        galleryObj['photo_1'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110226111728im_/http://gothamist.com/assets_c/2011/02/2011_02_uma-thumb-76x76-601056.jpg" title="" id="photo_2" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":2, "image": "https://web.archive.org/web/20110226111728/http://gothamist.com/upload/2011/02/2011_02_uma.jpg", "caption": "Uma Thurman reading to kids at the NYPL, as part of Target's <a href=\"http://reading.target.com/\">Read Across America</a> program", "credit":"Target"};
        galleryObj['photo_2'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110226111728im_/http://gothamist.com/assets_c/2011/02/2011_02_mark-thumb-76x76-601057.jpg" title="" id="photo_3" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "id":3, "image": "https://web.archive.org/web/20110226111728/http://gothamist.com/upload/2011/02/2011_02_mark.jpg", "caption": "Mark Ruffalo reading to kids at the NYPL, as part of Target's <a href=\"http://reading.target.com/\">Read Across America</a> program", "credit":"Target"};
        galleryObj['photo_3'] = photo;
    </script>
    <!--
    
    -->
    


</div></div><p>Let&apos;s cleanse our palate after that Dr. Seuss <a href="https://web.archive.org/web/20110226111728/http://gothamist.com/2011/02/08/dr_seuss_books_finally_get_raunchy.php">does burlesque</a> nightmare (yes, we had nightmares), with something a little more innocent. Our friends at the New York Public Library sent over this photo today, saying the Cat in the Hat stopped by the <a href="https://web.archive.org/web/20110226111728/http://gothamist.com/2011/02/03/unveiled_new_york_public_librarys_n.php">newly renovated</a> Stephen A. Schwarzman Building this morning. Not only did he say hello to one of the library&apos;s famed lions, but he also sat in on a reading of the author&apos;s stories with Mark Ruffalo and Uma Thurman.</p>