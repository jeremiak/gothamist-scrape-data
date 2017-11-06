---
author: Jen Carlson
date: February 23, 2011 12:40 PM
title: Flashback: The French Connection
---

	      <div class="galleryEase" id="gallery-0">

<!-- gallery js -->
<script type="text/javascript"> 

var galleryObj = new Object();
 
function gallerySwap(photoObj) {
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
    
    $('#galleryImg').attr('src', photoObj.image);
    $('.galleyEaseInfo').html(info);
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
        document.location.hash = 'photo-' + ($('.galleryEaseActiveThumbs img').index(this)+1);
        $('.galleryEaseThumb').addClass('galleryEaseActiveThumb').removeClass('galleryEaseThumb');
        $(this).removeClass('galleryEaseActiveThumb').addClass('galleryEaseThumb');
    });
    
    $('.galleryEaseNext').click(function() {
        if ($('.galleryEaseThumb').is(":last-child")) { // we're at the end, roll around
            var photoObj = galleryObj[$('.galleryEaseActiveThumb:first').attr('id')];
            
            gallerySwap(photoObj);
        
            $('.galleryEaseThumb').addClass('galleryEaseActiveThumb').removeClass('galleryEaseThumb');
            $('.galleryEaseActiveThumb:first').addClass('galleryEaseThumb').removeClass('galleryEaseActiveThumb');
            
        } else { 
            var photoObj = galleryObj[$('.galleryEaseThumb').next().attr('id')];
            
            gallerySwap(photoObj);
            
            $('.galleryEaseThumb').next().addClass('galleryEaseThumb').removeClass('galleryEaseActiveThumb');
            $('.galleryEaseThumb:first').addClass('galleryEaseActiveThumb').removeClass('galleryEaseThumb');
 
        }
        document.location.hash = 'photo-' + ($('.galleryEaseActiveThumbs img').index($('.galleryEaseThumb'))+1);
        
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
        document.location.hash = 'photo-' + ($('.galleryEaseActiveThumbs img').index($('.galleryEaseThumb'))+1);
    });
});
 
 
</script>
<!-- end gallery js -->


<!--start of gallery code-->
<a name="gallery"></a>
<div class="galleryEaseDisplayed">
<img id="galleryImg"><br>
<div class="galleyEaseInfo"></div>
<div class="galleryEaseNext"></div>
<div class="galleryEasePrev"></div>
</div>
<div class="galleryEaseThumbs">




    <img src="https://web.archive.org/web/20110225105833im_/http://gothamist.com/assets_c/2011/02/2eganfrenchconn-thumb-76x76-600009.jpg" title="" id="photo_1" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "image": "https://web.archive.org/web/20110225105833/http://gothamist.com/upload/2011/02/2eganfrenchconn.jpg", "caption": "\"Celebrity policeman Edward Egan, whose life the movie French Connection is based, at home.\" 1971.", "credit":""};
        galleryObj['photo_1'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110225105833im_/http://gothamist.com/assets_c/2011/02/eganfrenchconn0211-thumb-76x76-600012.jpg" title="" id="photo_2" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "image": "https://web.archive.org/web/20110225105833/http://gothamist.com/upload/2011/02/eganfrenchconn0211.jpg", "caption": "\"Policeman Eddie Egan interrogating suspect.\" 1971.", "credit":""};
        galleryObj['photo_2'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110225105833im_/http://gothamist.com/assets_c/2011/02/3eganfrenchconn0211-thumb-76x76-600010.jpg" title="" id="photo_3" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "image": "https://web.archive.org/web/20110225105833/http://gothamist.com/upload/2011/02/3eganfrenchconn0211.jpg", "caption": "\"Police officer/actor Eddie Egan poised on street, smoking cigarette, detective of 1962 <em>French Connection</em> heroin bust fame, cast opposite Gene Hackman in 1971 eponymous film.\"", "credit":""};
        galleryObj['photo_3'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110225105833im_/http://gothamist.com/assets_c/2011/02/4eganfrenchconn0211-thumb-76x76-600011.jpg" title="" id="photo_4" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "image": "https://web.archive.org/web/20110225105833/http://gothamist.com/upload/2011/02/4eganfrenchconn0211.jpg", "caption": "\"Policeman Eddie Egan attaching pistol to ankle in home.\" 1971.", "credit":""};
        galleryObj['photo_4'] = photo;
    </script>
    <!--
    
    -->
    

    <img src="https://web.archive.org/web/20110225105833im_/http://gothamist.com/assets_c/2011/02/eganfrenchconn02111-thumb-76x76-600018.jpg" title="" id="photo_5" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "image": "https://web.archive.org/web/20110225105833/http://gothamist.com/attachments/arts_jen/eganfrenchconn02111.jpg", "caption": "Detective Eddie Egan outside police precinct with some local kids. 1971.", "credit":""};
        galleryObj['photo_5'] = photo;
    </script>
    <!--
    
    -->
    <br>

    <img src="https://web.archive.org/web/20110225105833im_/http://gothamist.com/assets_c/2011/02/frenchconnhackman-thumb-76x76-600014.jpg" title="" id="photo_6" class="galleryEaseActiveThumb">    
    <script type="text/javascript">
        var photo = { "image": "https://web.archive.org/web/20110225105833/http://gothamist.com/attachments/arts_jen/frenchconnhackman.jpg", "caption": "Gene Hackman in The French Connection.", "credit":""};
        galleryObj['photo_6'] = photo;
    </script>
    <!--
    
    -->
    


</div></div><p>The late NYPD detective Eddie Egan gained fame after he helped bust up an organized crime ring in 1961 with his partner Sonny Grosso. They seized 112 lbs of heroin, and the investigation became the subject of a book by Robin Moore, called <em>The French Connection</em>. By 1971 the story was hitting the big screen, with Egan being portrayed by Gene Hackman (he won an Oscar for his performance&#x2014;the film also won Oscars for Best Picture, Director, Screenplay, and Editing). His character was called Jimmy &quot;Popeye&quot; Doyle&#x2014;the nickname being Egan&apos;s real life nickname. You can watch Hackman&apos;s Oscar acceptance speech <a href="https://web.archive.org/web/20110225105833/http://www.youtube.com/watch?v=Dk0hMxRtHWA">here</a>, and the movie&apos;s trailer below (along with that <a href="https://web.archive.org/web/20110225105833/http://www.popularmechanics.com/cars/news/vintage-speed/4270411-2">famous</a> car chase scene).</p>

<p><iframe title="YouTube video player" width="640" height="390" src="https://web.archive.org/web/20110225105833if_/http://www.youtube.com/embed/5A6ynmURxzM" frameborder="0" allowfullscreen></iframe></p>

<p><iframe title="YouTube video player" width="640" height="510" src="https://web.archive.org/web/20110225105833if_/http://www.youtube.com/embed/Hu3GmRQ-U9k" frameborder="0" allowfullscreen></iframe></p>

<p>Two years after <em>The French Connection</em>&apos;s release, Robert Duvall played the role of Egan in another (less successful) movie, called <a href="https://web.archive.org/web/20110225105833/http://en.wikipedia.org/wiki/Badge_373"><em>Badge 373</em></a>; this was a less fictionalized account of Egan&apos;s entire career.</p>