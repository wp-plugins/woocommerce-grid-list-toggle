=== WooCommerce Grid / List toggle ===
Contributors: jameskoster
Tags: woocommerce, grid, list, products, ecommerce
Requires at least: 3.3
Tested up to: 3.5
Stable tag: 0.3
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Adds a grid/list view toggle to product archives

== Description ==

WooCommerce Grid / List toggle is a simple plugin which adds a Grid / List toggle to your product archives allowing users to, you guessed it, toggle between grid / list views of your products.

The list view arranges products in a vertical list and pulls in the excerpt to give a more detailed overview.

The grid view you will be familiar with as this is WooCommerce's default layout for product archives.

The store owner can choose whether grid or list view be set as the default.

Please feel free to contribute on <a href="https://github.com/jameskoster/woocommerce-grid-list-toggle">github</a>.

== Installation ==

1. Upload `woocommerce-grid-list-toggle` to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Done!

== Frequently Asked Questions ==

= It doesn't work with my theme, what gives? =

You may see varied results depending on how the theme has been built and whether it's already pulling the excerpt into product archives. I've tried to cover all bases with CSS but it's likely you'll need to make your own adjustments. WooCommerce Grid / List toggle has been tested with Twenty Ten, Twenty Eleven and Twenty Twelve.

= I found and fixed a bug how can I help? =
Thanks! Please fork the repo on <a href="https://github.com/jameskoster/woocommerce-grid-list-toggle">github</a>, push your fix then send a pull request.

= I don't like the button styles, how can I remove them and start fresh? =
Add the following code to the functions.php file in your theme / child theme:

`
add_action( 'wp_enqueue_scripts', 'remove_gridlist_styles', 30 );
function remove_gridlist_styles() {
	wp_dequeue_style( 'grid-list-button' );
}
`

That will remove the button styles but keep the layout styles which will allow you to design the buttons as you see fit.

To remove the layout styles as well use:

`
add_action('get_header', 'remove_gridlist_styles', 30);
function remove_gridlist_styles() {
	wp_dequeue_style( 'grid-list-button' );
	wp_dequeue_style( 'grid-list-layout' );
}
`

== Screenshots ==

1. Example of products laid out in list view in Twenty Eleven

== Changelog ==

= 0.3 - 30/01/2013 =
* Added option to choose default view

= 0.2.3 - 28/01/2013 =
* Fixed active class bug on the toggle button
* Styled the star-rating in list view

= 0.2.2 - 16/01/2013 =
* Re-applied button style. See FAQ to remove
* YUI compressed CSS
* Styles loaded on product tag archives

= 0.2.1 - 10/01/2013 =
* Add active class to grid button on initial load

= 0.2 - 09/01/2013 =
* Delayed gridlist_toggle_button() priority for better WooCommerce 2.0 compatibility
* Even stricter CSS for list view (improves theme compatibility)
* Changed #gridlist-toggle to .gridlist-toggle

= 0.1.1 - 08/01/2013 =
* Set grid as default view
* Stricter CSS for list view
* Only add the excerpt on shop / product category pages
* Removed toggle button styling - this should be done in your theme

= 0.1 =
Initial release.