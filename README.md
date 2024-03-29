## **WordPress Theming with Webflow and Underscores**

  

**Webflow**

  

1) Design your site in Webflow.

  

2) Make at least one page that includes a header and a footer. Make sure to include a style guide that includes a rich media component with all of your H tags and other type defined.

  

3) As an example, design a blog post - Include a headline, a dek, a byline a main image and body text.

  

4) Export your code and prepare a .zip and then download the .zip to your desktop.

  

**UnderScores**

  

1) Navigate to [underscores.me](http://underscores.me/) and download a ready-made Word Press starter theme for your web site.

  

2) Underscores will export a folder with everything you need to make a working theme. It gives you a lot more pieces of code than you may need. It also gives you much code in the posts that you might not need.

  

4) Open your new _underscores theme folder in a text editor like Atom or Coda.

  

5) Grab the Webflow CSS files

  

- yourprojectname.webflow.css,

- weblow.css,

- normalize.css

  

Put these files in a new folder that you make called “CSS” in your new _underscores theme.

  

6) Grab the webflow.js file and place in the js folder in the _underscroes theme.

  

7) Open single.php delete everything between

`<?php get_header(); ?>` and `<?php get_sidebar(); get_footer();  ?>`

8) Open header.php

DELETE everything including and below <body <?php body_class(); ?>> then paste your webflow header code in that space.

  

9) Open footer.php

DELETE everything below and between `</div><!-- #content -->` and `<?php wp_footer(); ?>`

  

Paste your webflow footer code in that space.

  

**_Optional:_** To make your post look like your webflow design DELETE `get_sidebar();` otherwise you’ll be getting content appearing that you won’t know what to do with.

  

10) Then open the styles.css file in your _underscores theme folder. DELETE everything below the commented information at the top.

  

**Below**



    Normalizing styles have been helped along thanks to the fine work of
    
    Nicolas Gallagher and Jonathan Neal https://necolas.github.io/normalize.css/


  

_There should be no css styles in this file. You will point your functions file to your Webflow stylesheet instead of this file._

  

11) In your _underscores theme open functions.php. Scroll to the bottom put the following code which will point your theme to your new Webflow designed theme.

  


**Webflow theming**



	 //wp_deregister_style( 'style' );
    wp_enqueue_style( 'style', get_template_directory_uri() . '/style.css', false, null, 'all');
    
    //wp_deregister_style( 'thenewshousewebflow' );
    wp_enqueue_style( 'nhwebflow', get_template_directory_uri() . '/css/thenewshouse-wordcamp-edition.webflow.css', false, null, 'all');
    
    //wp_deregister_style( 'normalize' );
    wp_enqueue_style( 'normalize', get_template_directory_uri() . '/css/normalize.css', false, null, 'all');
    
    //wp_deregister_style( 'webflow' );
    wp_enqueue_style( 'webflow', get_template_directory_uri() . '/css/webflow.css', false, null, 'all');
    
    //wp_deregister_script( 'webflowjs' );
    wp_enqueue_script( 'webflowjs', '/js/webflow.js', false, null, false);

Then upload your new theme to theme area of your site:
wp-content/themes/

**WordPress & ACF**

Make sure the following Plugins are loaded:

 - Advanced Custom Fields Pro 
 - Classic Editor 
 - ThemeCode Pro

Make a new set of Custom Fields named Basic Story Page

Make the following fields:

Dek —> Text
Image —> Image
Caption —> Text
Byline —> Text
BodyCopy —> Text Area

Save Custom Field Set then Refresh — Look to Bottom of page and see your exported code.

In your code editor open your single post webflow design .html file.

Cut the code and then paste into the single.php template in your theme folder by replacing the dummy copy with your exported ACF variable code.

 **TIP:** For the headline or story post title use <?php the_title(''); ?>

In your Wordpress admin _Edit a New Pos_t - you will then be able to fill in specific ACF customfields that will then be output on your page exactly where you want them to be.

 **ACF and Flexible Fields**

  

In your Basic Story Page Custom Fields make the following field:

*Stripes —> Flexible Fields*  

***Layouts:***

*Image —> Image*
*Story Text —> Wysiwyg Editor*

  

Then you can add as many stripes as you wnat on one page an drag and drop then vertically on the page.




