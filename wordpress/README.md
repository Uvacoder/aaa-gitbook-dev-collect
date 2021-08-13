# WordPress

### 2021

|  |  |
| :--- | :--- |
| https://wptavern.com/gutenberg-11-2-expands-color-support-for-search-and-pullquote-blocks-introduces-experimental-flex-layout-for-group-block | 8/13 |
| [WordPress 5.8 Tatum](https://wordpress.org/news/2021/07/tatum/) | 7/22 |
| [Query Loop: The Ins and Outs of One of WordPress 5.8’s Most Powerful Features](https://wptavern.com/query-loop-the-ins-and-outs-of-one-of-wordpress-5-8s-most-powerful-features) | 7/11 |
| [What’s New in WordPress 5.8](https://kinsta.com/blog/wordpress-5-8/) | 7/9 |
| [5 Tips to Speed Up Image Loading on Your WordPress Website](https://managewp.com/blog/image-optimization-wordpress) | 1/14 |

### 2020

|  |  |
| :--- | :--- |
| [Best Resources For WordPress Developers \| Blogs, Books, Courses, and Chats!](https://www.youtube.com/watch?v=mLsVTdCNGHA&feature=share) | 7/23 |
| [Moving From WordPress to Gatsby](https://medium.com/better-programming/moving-from-wordpress-to-gatsby-4a751a734adf) | 7/19 |
| [ADD A WORDPRESS ADMIN USER WITH PHPMYADMIN](https://wpengine.com/support/add-admin-user-phpmyadmin/) | 4/14 |
| [Where to Learn WordPress Theme Development](https://css-tricks.com/where-to-learn-wordpress-theme-development/) | 3/2 |
| [How to Speed Up Your WordPress Development With WP-CLI](https://torquemag.io/2017/02/wordpress-development-with-wp-cli/) | 12/13/2019 |

| resources |  |
| :--- | :--- |
| [Codex](https://codex.wordpress.org/) |  |
| [Codex - function](https://codex.wordpress.org/Function_Reference) |  |
| [Dashicons](https://developer.wordpress.org/resource/dashicons/) | 12/13 |
| [Developer.wordpress](https://developer.wordpress.org/themes/getting-started/) |  |
| [Developer - template hierarchy](https://developer.wordpress.org/themes/basics/template-hierarchy/) |  |
| [Easy wp guide](https://easywpguide.com/) |  |
| [GenerateWP](https://generatewp.com/) |  |
| [Searchbar](https://wedevs.com/133739/add-search-bar-in-wordpress/) |  |

| subscription/blogs |  |
| :--- | :--- |
| [https://wptavern.com](https://wptavern.com) | 11/10 |

|  |  |
| :--- | :--- |
| [Actions](https://developer.wordpress.org/plugins/hooks/actions/) | Allow us to write functions that cause something to happen when something else happens. |
| [Hooks](https://developer.wordpress.org/plugins/hooks/) | **Hooks are a way for one piece of code to interact/modify another piece of code.** They make up the foundation for how plugins and themes interact with WordPress Core, but they’re also used extensively by Core itself. |
| Filters | Allow us to manipulate data or content |

```php
//temporary login hack
//place in functions.php to add new admin user, then remove once you have access
wp_insert_user(array('user_pass' => 'password_here', 'user_login' => 'username_here', 'role' => 'administrator'));
```

