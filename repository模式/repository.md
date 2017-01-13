# Laravel中Repository模式浅见

`在laravel强大的orm前提，为什么还要去考虑repository模式，是否多次一举？`
******
`在讨论此问题之前，先简单的回顾一下MVC模式`

### MVC浅析
- M:Model(模型)
- V:View(视图)
- C:Controller(控制器)

个人理解：Controller用于接收请求，然后去Model获取数据，再把数据渲染到View，最后把页面呈现给用户。

那么从MVC完成的功能上看，现在MVC已经很好的完成了分离数据和视图操作。

下面从具体需求出来，来讨论这个问题。

背景：文章下面有评论，文章是由用户写的。

1. 返回用户信息,直接使用orm

Laravel中Controller简单代码
```php
namespace App\Http\Controllers;

use App\User;
use App\Http\Controllers\Controller;

class UserController extends Controller
{
    /**
     * Show the profile for the given user.
     *
     * @param  int  $id
     * @return Response
     */
    public function show($id)
    {
        return view('user.profile', ['user' => User::findOrFail($id)]);
    }
}
```
很明显，控制器中直接获取model中数据，可以说很简单，很方便，也很直观。

2. 然后有时候，情况并不是这么简单，这里面，别的文章列表，