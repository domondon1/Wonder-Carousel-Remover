    // Add 'hidden' class
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

    // This script it will append after 3 seconds so that it will disregard the carousel code
    function wonder_script() {
        $url = 'a[href="http://www.wonderplugin.com/wordpress-carousel/"]';
        $script = "";
        $script .= "<script>";
        $script .= "jQuery(document).ready(function(){
            setTimeout(function() {
                jQuery('.amazingcarousel-image').find('".$url."').parent().addClass('hidden').removeAttr( 'style' );
            }, 3000);
        });";
        $script .= "</script>";
        echo $script;
    }


    add_action('wp_head', 'wonder_style');

    add_action('wp_head', 'wonder_script');
   
