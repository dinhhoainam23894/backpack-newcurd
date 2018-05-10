#### Đầu tiên phải cài đặt backpack theo hướng dẫn [Laravel Backpack](https://github.com/Laravel-Backpack)

#### Installation type (B) - package

1) ở terminal chạy:

``` bash
$ composer require namdh2/newscrud
```

2) Then add the service providers to your config/app.php file:

```
'Backpack\News\NewsCRUDServiceProvider',
```

3) Publish the migration:

```
php artisan vendor:publish --provider="Backpack\News\NewsCRUDServiceProvider"
```

4) Run the migration to have the database table we need:

```
php artisan migrate
```

5) [optional] Add a menu item for it in resources/views/vendor/backpack/base/inc/sidebar.blade.php or menu.blade.php:

```html
<li class="treeview">
    <a href="#"><i class="fa fa-newspaper-o"></i> <span>News</span> <i class="fa fa-angle-left pull-right"></i></a>
    <ul class="treeview-menu">
      <li><a href="{{ backpack_url('article') }}"><i class="fa fa-newspaper-o"></i> <span>Articles</span></a></li>
      <li><a href="{{ backpack_url('category') }}"><i class="fa fa-list"></i> <span>Categories</span></a></li>
      <li><a href="{{ backpack_url('tag') }}"><i class="fa fa-tag"></i> <span>Tags</span></a></li>
    </ul>
</li>
```
