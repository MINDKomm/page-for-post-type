# Page for Post Type

Allows you to set a page as the base URL for a post type, much like you can set a page for your blog posts.

This gives you some flexibility when using plugins or themes that provide custom post types. It's not unusual to want to nest these a little deeper in your site's page hierarchy.

## Usage

The plugin adds a settings section to the reading settings page where you would normally set a static home page and page for your posts.

You can choose a page to act as your post type archive page and also as the rewrite slug for posts within that post type.

The plugin will create a new option `page_for_{yourcpt}` in the `wp_options` table under which it will save the id of the page that will act as an archive for that post type.

### archive.php example

The default query will contain the posts to show in the archive. To get the data from your archive page, you can get the id of the page via `get_option` and then get the page data through `get_post`.

```php
$page_id = get_option( 'page_for_yourcpt' );
$page = get_post( $page_id );
```
