# WordPress

|  |  |
| :--- | :--- |
| [ADD A WORDPRESS ADMIN USER WITH PHPMYADMIN](https://wpengine.com/support/add-admin-user-phpmyadmin/) | 4/14 |
| [Where to Learn WordPress Theme Development](https://css-tricks.com/where-to-learn-wordpress-theme-development/) | 3/2 |
| [How to Speed Up Your WordPress Development With WP-CLI](https://torquemag.io/2017/02/wordpress-development-with-wp-cli/) | 12/13/2019 |

|  |  |
| :--- | :--- |
| [Codex](https://codex.wordpress.org/) |  |
| [Codex - function](https://codex.wordpress.org/Function_Reference) |  |
| [Developer.wordpress](https://developer.wordpress.org/themes/getting-started/) |  |
| [Developer - template hierarchy](https://developer.wordpress.org/themes/basics/template-hierarchy/) |  |
| [Easy wp guide](https://easywpguide.com/) |  |
| [GenerateWP](https://generatewp.com/) |  |
| [Searchbar](https://wedevs.com/133739/add-search-bar-in-wordpress/) |  |

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

