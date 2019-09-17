1.`【强制】`代码中的命名严禁使用拼音与英文混合的方式，更不允许直接使用中文的方式。
- 说明：正确的英文拼写和语法可以让阅读者易于理解，避免歧义。注意，纯拼音命名方式更要避免采用。
- 正例：$renminbi / $alibaba / $taobao / $youku / $hangzhou 等国际通用的名称，可视同英文。
- 反例：$DaZhePromotion [打折] / getPingfenByName() [评分] / $某变量 = 3

2.`【强制】`类名使用 UpperCamelCase 风格。
- 正例：StoreSiteAuditLogic / XmlService
- 反例：StoresiteauditLogic / XMLService

3.`【强制】`方法名、参数名、成员变量、局部变量都统一使用 lowerCamelCase 风格，必须遵
从驼峰形式。
- 正例： localValue / getHttpMessage() / inputUserId

4.`【强制】`常量命名全部大写，单词间用下划线隔开，力求语义表达完整清楚，不要嫌名字
长。
- 正例：MAX_STOCK_COUNT / CACHE_EXPIRED_TIME
- 反例：MAX_COUNT / EXPIRED_TIME

5.`【强制】`静态变量使用 s 开头；私有方法和私有变量使用 _ 开头；抽象类命名使用 Abstract 开头；异常类命名使用 Exception 结尾；测试类命名以它要测试的类的名称开始，以 Test 结尾。

6.`【强制】`不要使用global类型的全局变量，使用配置文件代替全局变量。

7.`【强制】`避免在子父类的成员变量之间、或者不同代码块的局部变量之间采用完全相同的命
名，使可读性降低。
- 说明：子类、父类成员变量名相同，即使是 public 类型的变量也是能够通过编译，而局部变量在同一方法
内的不同代码块中同名也是合法的，但是要避免使用。
- 反例：
```php
public function getData()
{
    $mainOrderDatas = ['TPA1001', 'TPA1002', 'TPA1003'];
    $detailOrderDatas = [
        ['TPA1001' => ['goods_no' => '001'],
        ['TPA1002' => ['goods_no' => '002'],
        ['TPA1003' => ['goods_no' => '003'],
    ];
    
    foreach ($mainOrderDatas as $data) {
        // ...
    }

    foreach ($detailOrderDatas as $data) {
        // 在同一方法体中，不允许与其它代码块中的 $data 命名相同
        // ...
    }
}
```

8.`【强制】`杜绝完全不规范的缩写，避免望文不知义。
- 反例：AbstractClass“缩写”命名成 AbsClass；condition“缩写”命名成 condi，此类随意缩写严重降低了代码的可阅读性。

9.`【强制】`为了达到代码自解释的目标，任何自定义编程元素在命名时，使用尽量完整的单词
组合来表达其意。
- 正例：在代码中，表达原子更新的类名为：AtomicReferenceFieldUpdater。
- 反例：int a 的随意命名方式。

10.`【推荐】`在常量与变量的命名时，表示类型的名词放在词尾，以提升辨识度。
- 正例：startTime / workQueue / nameList / TERMINATED_THREAD_COUNT
- 反例：startedAt / QueueOfWork / listName / COUNT_TERMINATED_THREAD

11.`【推荐】`如果模块、接口、类、方法使用了设计模式，在命名时需体现出具体模式。
- 说明：将设计模式体现在名字中，有利于阅读者快速理解架构设计理念
- 正例： 
 - class OrderFactory;
 - public class LoginProxy;
 - public class ResourceObserver;

12.`【参考】`Service/Model 层命名规约：
 1. 获取单个对象的方法用 `getItem`
 2. 获取多个对象的方法用 `getItems`
 3. 获取列表对象的方法用 `getList`
 4. 获取统计值的方法用 `getCount`
 5. 获取已某个值为键的数据方法用 `getCates` 
 5. 插入的方法用 `insert` 做前缀。
 6. 删除的方法用 `delete` 做前缀。
 7. 修改的方法用 `update` 做前缀。
 8. 插入和修改并存的方法用 `save` 做前缀。