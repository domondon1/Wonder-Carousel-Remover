<?php 
    /*
    Plugin Name: Wonder-Carousel Watermark Remover
    Plugin URI: https://github.com/domondon1/wonder-carousel-watermark-remove
    Description: This Wordpress plugin is for the wonder carousel it will remove the watermark of the carousel
    Author: Roderick Domondon
    Version: 1.sample
    Author URI: https://github.com/domondon1/wonder-carousel-watermark-remove
    */

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
    ?>
