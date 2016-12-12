# THIS SIMPLE PLUGIN is for Wonder Carousel 

This simple plugin will remove the watermark of the carousel

<code>
    
    function wonder_style() {
    	$style = "";
    	$style .= "<style>";
    	$style .= ".hidden{
    		visibility: hidden !important;
    		width:0 !important;
    		height: 0 !important;
    		padding: 0 !important;
    		overflow: hidden !important;
    	}";
    	$style .= "</style>";
    	echo $style;
    }

   
    function wonder_script() {
    	$url = "http://www.wonderplugin.com/wordpress-carousel/";
    	$script = "";
    	$script .= "<script>";
    	$script .= "jQuery(document).ready(function(){
    		setTimeout(function() {
    			jQuery('.amazingcarousel-image').find('a[href=".$url."]').parent().addClass('hidden').removeAttr( 'style' );
    		}, 3000);
    	});";
    	$script .= "</script>";
    	echo $script;
    }
    
    </code>
  ------
  
  So this will append on the HTML the output for this
  <code>
  .hidden{
    		visibility: hidden !important;
    		width:0 !important;
    		height: 0 !important;
    		padding: 0 !important;
    		overflow: hidden !important;
    	}
  

  jQuery(document).ready(function(){
    		setTimeout(function() {
    			jQuery('.amazingcarousel-image').find('a[href=http://www.wonderplugin.com/wordpress-carousel/]').parent().addClass('hidden').removeAttr( 'style' );
    		}, 3000);
    	});
</code>
