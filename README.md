<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Laravel Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

# Geekor's Laravel Template

## 初次使用

安装依赖

```sh
# 安装依赖
composer install

# 生成 .env 配置文件
php -r "file_exists('.env') || copy('.env.example', '.env');"

# 生成 APP KEY
php artisan key:generate --ansi

# 修改 数据库连接相关的配置
vim .env
```

一键配置项目

```sh
./vendor/geekor/laravel-backend-master/scripts/install-module.sh
```

详细说明，请参考： [https://github.com/Geekor/laravel-backend-master](https://github.com/Geekor/laravel-backend-master)  

## 创建模块

以创建 Article 模块为例

```sh
php artisan bm:make-module Article articles
```
你会看到类似下面的打印

```txt
 # bm:make-module
            {model : model name}
            {table : database table name}

Generate Module to: /home/vagrant/code/templates-demo/_modules/Article

new migration:
+------+-------------------------------------------------------+-------+
| Ran? | Migration                                             | Batch |
+------+-------------------------------------------------------+-------+
| Yes  | 2014_10_12_000000_create_users_table                  | 1     |
| Yes  | 2014_10_12_100000_create_password_resets_table        | 1     |
| Yes  | 2019_08_19_000000_create_failed_jobs_table            | 1     |
| Yes  | 2019_12_14_000001_create_personal_access_tokens_table | 1     |
| No   | 2022_05_23_055332_create_articles_table               |       |
+------+-------------------------------------------------------+-------+
new routes:

  GET|HEAD  api/articles ..................... Modules\Article\Normal\Http\Controllers\Api\ArticleController@index
  POST      api/articles ..................... Modules\Article\Normal\Http\Controllers\Api\ArticleController@store
  DELETE    api/articles ................... Modules\Article\Normal\Http\Controllers\Api\ArticleController@destroy
  GET|HEAD  api/articles/{id} ................. Modules\Article\Normal\Http\Controllers\Api\ArticleController@show
  PUT       api/articles/{id} ............... Modules\Article\Normal\Http\Controllers\Api\ArticleController@update
  GET|HEAD  api/backend/articles ............ Modules\Article\Backend\Http\Controllers\Api\ArticleController@index
  POST      api/backend/articles ............ Modules\Article\Backend\Http\Controllers\Api\ArticleController@store
  DELETE    api/backend/articles .......... Modules\Article\Backend\Http\Controllers\Api\ArticleController@destroy
  GET|HEAD  api/backend/articles/{id} ........ Modules\Article\Backend\Http\Controllers\Api\ArticleController@show
  PUT       api/backend/articles/{id} ...... Modules\Article\Backend\Http\Controllers\Api\ArticleController@update

```

## 测试
> 文档： [https://learnku.com/docs/laravel/9.x/testing/12257](https://learnku.com/docs/laravel/9.x/testing/12257)  
> HTTP 测试：  [https://learnku.com/docs/laravel/9.x/http-tests/12258](https://learnku.com/docs/laravel/9.x/http-tests/12258)  

通常，你的大多数测试应该是功能测试。这些类型的测试可以最大程度地确保你的系统作为一个整体按预期运行。

```sh

# 新建测试
php artisan make:test UserTest

# 运行测试
php artisan test

# 并行运行测试
php artisan test --parallel

# 报告测试覆盖率
php artisan test --coverage

# 最小覆盖率阈值限制
php artisan test --coverage --min=80.3

```

一个简单的测试用例。

```php
<?php
namespace Tests\Unit;
use PHPUnit\Framework\TestCase;
class ExampleTest extends TestCase
{
    public function test_basic_test()
    {
        $this->assertTrue(true);
    }
}
```

## Laravel 文档

- 推荐的中文文档： [https://learnku.com/docs/laravel/9.x](https://learnku.com/docs/laravel/9.x)

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
