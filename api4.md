# 1.fullList 品牌列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(array('id'=>$id,'name'=>$name)),'msg'=>'')
 fail:
array('status'=>1,'msg'=>'')
```
# 2.fullListPage 品牌列表--包含品牌下sku数,库存数
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |page|int|页码|可选|
<br> |limit|int|每页数量|可选|
<br>### 返回信息:
```php
 success:
array('status' => 0, 'data' => array('total'=>$data['total'],'page' => $data['page'],'limit'=>$data['limit'], 'list' => $ret))
```
# 3.add 添加品牌
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |name|string|品牌名称|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'msg'=>'')
 fail:
array('status'=>1,'msg'=>'失败')
```
# 4.stockList 品牌下商品列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array(array("id"=>$brand["id"],"name"=>$brand["name"],"sku"=>count($pids),"stock"=>$stocks))
```
# 5.del 删除品牌
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |id|int|品牌id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
array('status'=>1, 'msg' => $msg)
```
# 6.boqiiList 波奇品牌列表
     
### version:  1.0
     
### author:  fangyong
     
### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(array('id'=>'','name'=>''))
```
# 7.categoryList 获取商户的商品分类列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array(
    array(
    "id"=>"1",
    "pid"=>"0",
    "name"=>"犬",
    "level"=>"1",
    "bpath"=>"0-1",
    "type"=>"1",
    "create_time"=>"1419919674",
    "update_time"=>"1419919674",
    "count"=>2,
    "goods_num"=>"40"
    ),
    )
```
# 8.simpleCategoryList 商户商品分类列表(包含分类下的商品数量和库存数)
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array(
    array(
    "id"=>"1",
    "name"=> "犬",
    "level"=> "1",
    "type"=> "1",
    "goods_num"=> "40",
    "childList"=>array(
    array(
    "id"=> "6",
    "pid"=> "1",
    "name"=> "宠物狗粮",
    "level"=> "2",
    "type"=> "1",
    "goods_num"=> "2"
    ),
    array(
    "id"=> "7",
    "pid"=> "1",
    "name"=> "狗罐头/妙鲜包",
    "level"=> "2",
    "type"=>"1",
    "goods_num"=> "0"
    ),
     )
```
# 9.addCategory 添加商品分类
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |ids|父级分类id|int|可选|
<br> |name|分类名称|string|必填|
<br> |bid|商户id|int|必填|
<br> |uid|操作人id|int|可选|
<br>### 返回信息:
```php
 success:
array(
    "status"=> 0,
    "data"=>array(
    "id"=> "291",
    "name"=> "kids",
    "pid"=> "2",
    "level"=> "2",
    "goods_num"=> "0"
    )
    )
```
# 10.editCategory 编辑分类信息
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|分类id|必填|
<br> |name|string|分类名称|必填|
<br> |uid|int|操作人id|可选|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array(
    "status"=> 0
    )
 fail:
array(
    "status"=> 1,
    "msg"=>"修改失败,分类未修改或该名称已被使用"
    )
```
# 11.delCategory 删除分类
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |id|int|分类id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,)
 fail:
array('status'=>1,'msg'=>'错误信息')
```
# 12.boqiiCategoryList 波奇分类列表
     
### author:  fangyong
     
### 返回信息:
```php
 success:
array(
    array(
    "id"=>"1",
    "name"=> "犬",
    "level"=> "1",
    "type"=> "1",
    "goods_num"=> "40",
    "childList"=>array(
    array(
    "id"=> "6",
    "pid"=> "1",
    "name"=> "宠物狗粮",
    "level"=> "2",
    "type"=> "1",
    "goods_num"=> "2"
    ),
    array(
    "id"=> "7",
    "pid"=> "1",
    "name"=> "狗罐头/妙鲜包",
    "level"=> "2",
    "type"=>"1",
    "goods_num"=> "0"
    ),
    )
```
# 13.clerkList 店员列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |name|string|店员姓名|可选|
<br> |mobile|string|电话号码|可选|
<br> |startTime|string|入店时间-开始|可选|
<br> |endTime|string|入店时间-结束|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(
        'total'=>'',
        'page'=>'',
        'limit'=>'',
        'list'=>array(
            'id'=>'店员id',
            'name'=>'店员姓名',
            'mobile'=>'店员电话',
            'into_shop_time'=>'入店时间',
            'clerk_user'=>'用户名',
            'service_num'=>'服务次数',
            'commission_amount'=>'提成总额',
            'settlement_num'=>'结算次数',
            'settlement_amount'=>'结算总额',
            'not_settlement_num'=>'未结次数',
            'not_settlement_amount'=>'未结次数'
        )
     ))
 fail:
array('status'=>1,'msg'=>'错误信息')
```
# 14.commissionList 店员提成列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |id|int|店员id|可选|
<br> |name|string|店员姓名|可选|
<br> |status|int|提成状态(已结/未结)|可选|
<br> |page|int|页码|可选|
<br> |num|int|分页数量|可选|
<br>### 返回信息:
```php
 success:
array('status' => 0, 'data' => array(
        'page'=>'页码',
        'total'=>'总条数',
        'limit'=>'分页数量',
        'list'=>array(
            'id'=>'提成id',
            'service_id'=>'服务id',
            'clerk_id'=>'店员id',
            'clerk_name'=>'店员姓名',
            'service_time'=>'服务时间',
            'service_content'=>'服务内容',
            'status'=>'结算状态',
            'pay_money'=>'付款金额',
            'rate'=>'提成比例',
            'get_money'=>'提成金额',
            'service_name'=>'服务名称'
        )
     ))
 fail:
array('status' => 1, 'msg' => '缺少必要参数')
```
# 15.clerkDetail 店员详情
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |id|int|店员id|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0, 'data' => array(
        'id'=>'店员id',
        'name'=>'店员姓名',
        'mobile'=>'店员电话',
        'into_shop_time'=>'入店时间',
        'clerk_pwd'=>'店员密码',
        'introduce'=>'店员信息',
        'img_path'=>'头像图片地址',
        'level'=>'店员级别'
        )
     )
 fail:
array('status' => -1001, 'msg' => '缺少必要参数')
```
# 16.addClerk 增加/编辑店员
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |name|string|店员姓名|必填|
<br> |mobile|string|店员电话|可选|
<br> |level|int|店员等级|必填|
<br> |time|string|入店时间|可选|
<br> |passwd|string|密码|必填|
<br> |info|string|店员备注信息|可选|
<br> |img_path|string|店员头像地址|可选|
<br> |bid|int|商户id|必填|
<br> |o2o_business_id|int|o2o商户id|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
array('status'=>1,'msg'=>'错误信息')
```
# 17.delClerk 删除店员
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|店员id|必填|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0)
 fail:
array('status' => -1002, 'msg' => '操作失败')
```
# 18.editClerk 编辑店员
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |name|string|店员姓名|必填|
<br> |mobile|string|店员电话|可选|
<br> |level|int|店员等级|必填|
<br> |time|string|入店时间|可选|
<br> |clerk_pwd|string|密码|可选|
<br> |info|string|店员备注信息|可选|
<br> |bid|int|商户id|必填|
<br> |id|int|店员id|必填|
<br> |img_path|string|头像地址|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
array('status'=>1,'msg'=>'错误信息')
```
# 19.addLevel 添加/修改店员级别
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |data|array|店员信息array('id'=>'级别id','name'=>'级别名称')|必填|
<br> |serviceType|string|所有的服务项目|必填|
<br> |serviceId|string|选择的服务项目|必填|
<br> |serviceRate|string|提成比例|必填|
<br> |bid|int|商户id|必填|
<br> |o2oBusinesId|int|o2o商户id|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
array('status' => 1, 'msg' => '缺少必要参数')
```
# 20.levelList 级别列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0, 'data' => array(
        'id'=>'级别id',
        'name'=>'级别姓名',
        'PercentageList'=>array(
            'ServiceId' => '服务id',
            'name' => '服务名称',
            'Percentage' => '提成比例',
            'status' => '设置状态',
        )
     ))
 fail:
array('status' => 1, 'msg' => '错误信息')
```
# 21.permissionList 权限列表--暂未使用

# 22.changePwd 店员修改密码
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |clerkId|string|店员id|必填|
<br> |newPass|string|新密码|必填|
<br> |oldpass|string|旧密码|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0)
 fail:
array('status' => -1003|-1004|-1005, 'msg' => '密码错误|操作失败|密码不对')
```
# 23.commissionOk 店员提成结算,支持批量结算,多个记录使用逗号分隔
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |commissionId|int|店员提成id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0)
```
# 24.getClerkListOneArr  获取店员列表
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('id'=>'店员id','name'=>'店员姓名')
```
# 25.delCommission 店员提成信息删除
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|店员提成id|必填|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0)
 fail:
array('status' => -1001|-1002, 'msg' => '缺少必要参数|操作失败')
```
# 26.delLevel 店员等级删除
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|级别id|必填|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0)
 fail:
array('status' => -1001|-1002, 'msg' => '缺少必要参数|操作失败')
```
# 27.gradeInformation 店员等级信息
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|级别id|必填|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0, 'data' => array(
        'name'=>'级别名称',
        'server'=>array(
            'service_id'=>'服务id',
            'royalty_rate'=>'服务比例',
        )
     ))
 fail:
array('status' => -1001, 'msg' => '缺少必要参数')
```
# 28.businessList 商户点评列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |o2obid|int|生活馆id|必填|
<br> |clerkId|int|店员id|可选|
<br> |nickname|string|用户昵称|可选|
<br> |status|int|是否回复|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br>### 返回信息:
```php
 success:
array(
        'total'=>'总条数',
        'list'=>array(
            array(
            'yz_time'=>'验证时间',
            'content'=>'评论内容',
            'strAllTagName'=>'评价标签',
            'nickname'=>'用户昵称',
            'mobile'=>'电话号码',
            'clerkName'=>'店员名称',
            'is_reply'=>'是否回复',
            'replayContent'=>'回复内容',
            'couponTitle'=>'服务项目',
            'price'=>'价格',
            'avatar'=>'用户头像',
            ),
        )
     )
```
# 29.reply 回应点评
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|评论id|必填|
<br> |reply|string|回应内容|必填|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,)
 fail:
array('status'=>1,'msg'=>'错误消息')
```
# 30.batchReply 批量回应
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |ids|string|评论id(逗号分隔)|必填|
<br> |reply|string|回应内容|必填|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,)
 fail:
array('status'=>1,'msg'=>'错误消息')
```
# 31.saveReply 编辑回复
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|评论id|必填|
<br> |reply|string|回应内容|必填|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,)
 fail:
array('status'=>1,'msg'=>'错误消息')
```
# 32.loginCheck  登录检测
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |username|string|用户名|必须|
<br> |password|string|密码|必须|
<br> |usertype|int|用户类型|必须|
<br>### 返回信息:
```php
 success:
array(
    'status'=>'succ',
    'data'=>array(
    'user_name'     =>  '用户名',
    'userid'        =>  '用户id',
    'businessid'    =>  '商户id',
    'o2oBusinessid' =>  'o2o商户id',
    'role'          =>  1/2,
    'imgPath'       =>  '头像地址',
    'businessName'  =>  '商户名称',
    'businessCode'  =>  '商户编号',
    'authToken' => '授权token',
    'expires' => '过期时间',
    'businessTel'   =>  '商户电话号码')))
```
# 33.updatePassword  修改密码
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |userid|int|用户id|必须|
<br> |oldpassword|string|旧密码|必须|
<br> |newpassword|string|新密码|必须|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
array('status'=>1,'msg'=>'新密码不能为空|旧密码不能为空|旧密码错误|操作失败')
```
# 34.getSmsAlerts  获取商户短信通知设置信息和商户名称
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必须|
<br>### 返回信息:
```php
 success:
array(array(array('id','business_id','status','mobile'),)),'商户姓名')
```
# 35.editSmsAlerts  编辑商户短信通知设置
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必须|
<br> |mobile|string|商户mobile|必须|
<br> |status|int|状态|必须|
<br>### 返回信息:
```php
 success:
true
 fail:
false
```
# 36.businessList 会员列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |code|string|会员编号|可选|
<br> |name|string|会员名称|可选|
<br> |petName|string|宠物名称|可选|
<br> |petc1|int|宠物一级分类|可选|
<br> |petc2|int|宠物二级分类|可选|
<br> |createDate|string|会员创建时间|可选|
<br> |mobile|string|会员电话号码|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br> |export|int|是否导出|可选|
<br>### 返回信息:
```php
 success:
array(
        'status'=>0,
        'data'=>array(
        'total'=>$memberModel->total,
        'list'=>array(
            array(
                'id'=>'会员id',
                'code'=>'会员编号',
                'consume'=>'会员消费总计',
                'levelid'=>'会员等级',
                'level'=>'会员等级名称',
                'discount'=>'会员折扣比例',
                'name'=>'会员姓名',
                'mobile'=>'会员电话',
                'create_time'=>'会员创建时间',
                'balance'=>'会员余额',
                'remark'=>'会员备注'
            ),
        )
        )
     
```
# 37.recharge 会员充值
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |code|string|会员编号|必填|
<br> |money|float|充值金额|必填|
<br> |op|int|操作人id|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0, 'msg'=>"充值成功")
 fail:
array('status'=>1, 'msg'=>"充值失败")
```
# 38.del 会员删除
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |ids|int|会员id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
array('status'=>1,'msg'=>'删除失败')
```
# 39.addLevel 添加会员级别
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |level|string|级别名称|必填|
<br> |discount|float|折扣|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
array('status'=>1,'msg'=>'添加失败')
```
# 40.updateLevel 修改级别信息
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |id|int|会员级别id|必填|
<br> |level|string|会员级别名称|必填|
<br> |discount|float|级别折扣|必填|
<br>### 返回信息:
```php
 success:
array('status'=>1,'msg'=>'修改失败')
 fail:
array('status'=>0)
```
# 41.deleteLevel  删除级别
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |id|int|会员级别id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'msg'=>'删除成功')
 fail:
array('status'=>1,'msg'=>'删除失败')
```
# 42.levelList 会员级别列表
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
        array(
            array(
                'id'=>'级别id',
                'name'=>'级别名称',
                'business_id'=>'商户id',
                'discount'=>'折扣',
                'create_time'=>'创建时间',
                'update_time'=>'更新时间',
            ),
    )
```
# 43.addOrEditMember 添加/编辑会员
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |memberId|int|会员id|可选|
<br> |name|string|会员姓名|必填|
<br> |mobile|string|会员电话|必填|
<br> |balance|float|会员余额|可选|
<br> |level|int|会员级别|必填|
<br> |remark|string|会员备注|必填|
<br> |petinfo|string|宠物信息|可选|
<br>### 返回信息:
```php
 success:
array('status' => 0, 'msg' => '修改成功')
 fail:
array('status' => 1, 'msg' => '操作失败|手机号不可用')
```
# 44.checkMobileAvailable 检查手机号是否可用
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |mobile|string|手机号|必填|
<br> |memberId|int|会员id|可选|
<br>### 返回信息:
```php
 success:
array('status' => 0)
 fail:
array('status' => 1, 'msg' => '手机号格式不正确|手机号已被使用')
```
# 45.type 获取宠物种类
     
### version:  1.0
     
### author:  unknown
     
### 返回信息:
```php
 success:
array(array('id'=>'宠物种类id','name'=>'宠物种类名称'),)
```
# 46.varieties 宠物品种
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|宠物种类id|必填|
<br>### 返回信息:
```php
 success:
array(array('id'=>'宠物种类id','name'=>'宠物种类名称'),)
```
# 47.getMemberInfo  获取会员信息
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |mid|int|会员id|必填|
<br>### 返回信息:
```php
 success:
array(
            'id'=>'会员id',
            'business_id'=>'商户id',
            'code'=>'商户编号',
            'name'=>'会员姓名',
            'mobile'=>'会员电话',
            'balance'=>'会员余额',
            'total_money'=>'会员累计消费',
            'levelName'=>'级别名称',
            'dis'=>'折扣',
            'petList' => array(
                array(
                    'genderName' => '宠物性别',
                    'type'=>'宠物种类',
                    'variety'=>'宠物品种',
                ),
            )
    )
 fail:
false
```
# 48.searchMember  查询会员
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |keys|string|姓名/编号/手机号|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(
        array(
        'id'=>'会员id',
        'code'=>'会员编号',
        'levelid'=>'会员级别id',
        'level'=>'会员级别名称',
        'discount'=>'会员折扣',
        'name'=>'会员姓名',
        'mobile'=>'会员手机号',
        'balance'=>'会员余额',
        ),
    ))
```
# 49.createCode 生成商品编号
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>'商品编号')
```
# 50.addOrEdit 商品添加和编辑接口
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |id|int|商品id|可选-不填为新增商品|
<br> |name|string|商品名称|新增时必填|
<br> |img_path|string|商品图片路径|可选|
<br> |code|string|商品编号|新增时必填|
<br> |brandId|int|分类id|新增时必填|
<br> |salePrice|float|商品零售价|可选|
<br> |businessPrice|float|商品进货价|可选|
<br> |standard|float|商品规格|可选|
<br> |barcode|string|商品条码|可选|
<br> |stockNum|int|库存数量|可选|
<br> |stockWaringValue|int|库存警戒值|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0,'msg'=>''
 fail:
'status'=>1,'msg'=>'失败'
```
# 51.fullList 商品列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |businessCode|string|商品编号或者名称|可选|
<br> |categoryId|id|商品分类id|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br> |export|0/1|是否为导出列表|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(array('id','code','img_path','name','standard','pay_price','update_time','brand_name','category_name')))
```
# 52.searchProducts 出入库模块商品查询
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |keyword|商品名称或者编号|可选||
<br> |category|int|商品分类id|可选|
<br> |brand|int|品牌id|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>$list)
```
# 53.del 商品删除
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |ids|int|商品id,多个商品id以逗号分隔|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'msg'=>'')
 fail:
array('status'=>1,'msg'=>'删除失败')
```
# 54.detail 商品详情
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |MerchantId|int|商户id|必填|
<br> |GoodsId|int|商品id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(GoodsImg,
    GoodsTitle,
    GoodsNo,
    GoodsBrandId ,
    GoodsBrand,
    GoodsCategoryId ,
    GoodsSubCategoryId,
    GoodsChannelId ,
    GoodsChannel,
    GoodsBuyPrice ,
    GoodsSalePrice,
    GoodsCode,
    GoodsStock,
    GoodsWarningStock,
    GoodsSpec,
    GoodsDepth))
```
# 55.unpacking 商品拆包
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |operateUid|int|操作人id|可选|
<br> |goodsId|int|商品id|必填|
<br> |goodsNum|int|拆包数量|必填|
<br> |standard|float|拆包后规格|必填|
<br>### 返回信息:
```php
 success:

 fail:

```
# 56.unpackingCount 商品拆包计算
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |goodsId|int|商品id|必填|
<br> |goodsNum|int|拆包数量|必填|
<br> |standard|int|拆包后规格|必填|
<br>### 返回信息:
```php
 success:

 fail:

```
# 57.update 更新商品信息
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |MerchantId|int|商户id|必填|
<br>
# 58.importVerify 商品导入验证
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |operator|int|操作人id|可选|
<br> |files|string|导入excel文件信息|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,)
```
# 59.import 商品导入
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |operator|int|操作人id|可选|
<br> |updateStock|0|1|是否更新库存-若为否,不更新已存在商品库存||
<br> |overWrite|0|1|是否更新商品信息-若为否,不更新商品库存||
<br>### 返回信息:
```php
 success:
array('status'=>0,)
```
# 60.boqiiList 波奇商品列表-进货商品列表
     
### version:  1.0
     
### author:  fangyong
     
### 返回信息:
```php
 success:
array()
```
# 61.simpleNameList  商品简易名称列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |page|int|页码|必填|
<br> |limit|int|分页数量|必填|
<br>### 返回信息:
```php
 success:
array()
```
# 62.search_qrcode 凭证查询
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |qrcode|string|凭证码|必填|
<br> |o2oBusinessId|int|o2o商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=> array(
        'title' => '',
        'type' => '',
        'price' => '',
        'time' => '',
        'is_valid_end' =>'',
        'last' => '',
        'used' => '',
        'items' => '',
        )
     )
 fail:
array('status'=>1,'msg'=>'查无此券')
```
# 63.use_qrcode 消券
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |qrcode|string|券号|必填|
<br> |num|int|数量|必填|
<br> |o2oBusinessId|int|o2o商户id|必填|
<br>### 返回信息:

# 64.qrcodeList
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |o2oBusinessId|int|o2o商户id|必填|
<br> |startTime|string|开始时间|可选|
<br> |endTime|string|结束时间|可选|
<br> |qrcode|string|凭证码|可选|
<br> |p|int|页码|可选|
<br> |pagesize|int|分页数量|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(
        'qrcodeCount'=>'总条数',
        'qrcodeList'=>array(
        'id_code'=>'凭证码',
        'lastNum'=>'剩余次数',
        'goods_name'=>'商品名称',
        'discount_price'=>'折扣价格'
    ))
```
# 65.exportQrcodeList
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |o2oBusinessId|int|o2o商户id|必填|
<br> |startTime|string|开始时间|可选|
<br> |endTime|string|结束时间|可选|
<br> |qrcode|string|凭证码|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(
        'qrcodeCount'=>'总条数',
        'qrcodeList'=>array(
        'id_code'=>'凭证码',
        'lastNum'=>'剩余次数',
        'goods_name'=>'商品名称',
        'discount_price'=>'折扣价格'
    ))
```
# 66.saleOrderInfo 销售单详情
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |saleOrderId|int|销售单id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(
     'id'=>'销售单id',
     'code'=>'销售单号',
     'total'=>'商品总数',
     'pay_type'=>'支付类型',
     'product'=>array(
        'name'=>'商品名称',
        'product_code'=>'商品编号',
        'goodsType'=>'商品类型'
     )))
     
```
# 67.saleOrderList  销售单列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |productCode|int|商品编号|可选|
<br> |productTitle|string|商品名称|可选|
<br> |userType|int|用户类型(会员|非会员)|可选|
<br> |userName|string|用户名|可选|
<br> |starttime|string|购买时间|可选|
<br> |endtime|string|购买时间|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br>### 返回信息:
```php
 success:
array(
        'status'=>0,
        'total'=>'销售单总数',
        'data'=>array(
            'id'=>'销售单',
            'code'=>'销售单单号',
            'create_time'=>'下单时间',
            'user_name'=>'购买人姓名',
            'user_type'=>'用户类型(会员|非会员)',
            'user_mobile'=>'用户手机号',
            'total_money'=>'总计金额',
            'balance_pay'=>'余额支付金额',
            'cash_pay'=>'现金支付金额',
            'pay_type'=>'支付类型',
            'pay_type_name'=>'支付类型名称',
            'entity_num'=>'实物数量',
            'service_num'=>'服务数量'
     ))
```
# 68.exportSalesOrdersList 导出销售单列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |productCode|int|商品编号|可选|
<br> |productTitle|string|商品名称|可选|
<br> |userType|int|用户类型(会员|非会员)|可选|
<br> |userName|string|用户名|可选|
<br> |starttime|string|购买时间|可选|
<br> |endtime|string|购买时间|可选|
<br>### 返回信息:
```php
 success:
array(
        'status'=>0,
        'total'=>'销售单总数',
        'data'=>array(
        'id'=>'销售单',
        'code'=>'销售单单号',
        'create_time'=>'下单时间',
        'user_name'=>'购买人姓名',
        'user_type'=>'用户类型(会员|非会员)',
        'user_mobile'=>'用户手机号',
        'total_money'=>'总计金额',
        'balance_pay'=>'余额支付金额',
        'cash_pay'=>'现金支付金额',
        'pay_type'=>'支付类型',
        'pay_type_name'=>'支付类型名称',
        'entity_num'=>'实物数量',
        'service_num'=>'服务数量'
     ))
```
# 69.createOrder 确认售出-下单接口
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |ids|string|商品和服务id(以逗号分隔)|必填|
<br> |goods_num|string|商品和服务数量(以逗号分隔)|必填|
<br> |goods_price|string|商品金额(以逗号分割)|必填|
<br> |clerk_id|string|服务店员id(以逗号分割,商品对于的店员id为空)|可选|
<br> |member_id|int|会员id|可选|
<br> |pay_type|int|支付类型|必填|
<br> |total_money|float|订单金额|必填|
<br> |bid|int|o2o商户id|可选|
<br> |operator|int|操作人id|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
array('status'=>1,'msg'=>'失败信息')
```
# 70.hotProduct  热销商品查询
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array(
        'goods_id' => '商品id',
        'img_path' => '商品图片地址',
        'code' => '商品编号',
        'price' => '商品价格',
        'standard' => '商品规格',
        'brand' => '商品品牌名'
      )
```
# 71.getTemplateByServiceId  获取分类初始模版
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |serviceId|int|服务价目表ID|必须|
<br>
# 72.servicePriceDetail 服务价目表详情
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必须|
<br> |serviceId|int|服务价目表ID|必须|
<br>
# 73.addOrEditService 添加或编辑服务价目表
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |data|string|价目表数据(数据格式与价目表详情一致)|必填|
<br>### 返回信息:
```php
 success:
 success(array('status'=>0,)
 fail:
array('status'=>1,'msg'=>'错误信息')
```
# 74.serviceList 价目表列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(array('id'=>'价目表id','name'=>'价目表名称')))
```
# 75.serviceDetailList 价目表详情列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array('data(格式参见价目表详情)',))
 fail:
array('status'=>1,'msg'=>'错误信息')
```
# 76.delServicePrice
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必须|
<br> |serviceId|int|价目表Id|必须|
<br>### 返回信息:
```php
 success:
array('status'=>0, 'msg'=>'成功')
 fail:
array('status'=>1, 'msg'=>'删除失败')
```
# 77.cartList 购物车列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |business_id|int|商户id|必须|
<br> |page|int|页码|可选|
<br> |pageNum|int|分页数量|可选|
<br>### 返回信息:
```php
 success:

```
# 78.addcart 添加购物车
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |ids|int|商品id|必填|
<br> |business_id|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'num'=>'购物车商品数量')
 fail:
array('status'=>1,'msg'=>'添加失败')
```
# 79.delcart 删除购物车
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |ids|string|商品id(逗号分隔)|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'num'=>'购物车商品数量')
 fail:
array('status'=>1,'msg'=>'删除失败')
```
# 80.ChangeCart 购物车修改
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |MerchantId|int|商户id|必填|
<br> |OperatorId|int|操作人id|可选|
<br> |GoodsList|int|商品id|必填|
<br> |GoodsNum|int|变更数量|可选|
<br> |mark|string|变更类型(plus/reduction)|必填|
<br>### 返回信息:
```php
 success:
'goodsNum'
 fail:
0
```
# 81.cartNum  获取购物车中的商品数量
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:
'goodsNum'
```
# 82.comprehensiveStatistics  综合统计报表
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |o2obid|int|o2o商户id|必填|
<br>### 返回信息:
```php
 success:
array (
    'goodsSalesVolume' => 0,
    'serviceSalesVolume' => 0,
    'serviceSettleVolume' => 0,
    'goodsSalesProfit' => 0,
    'serviceSalesProfit' => 0,
    'commentsCount' => '0',
    'lastMonthSaleDayList' => '天数列表,逗号分隔',
    'lastMonthSaleMoneyList' => '对于天数的交易额',
    'endTime' => 1451318399,
    'startTime' => '2015-11-28',
    'monthSaleProductTop5' =>
    array (
    1 =>
    array (
    'order' => 1,
    'title' => '777',
    'brand_name' => '德丰宠物',
    'img_path' => '图片地址',
    'nowNum' => '94',
    'prevNum' => 0,
    ),
    ),
    'serviceSettleData' => NULL,
    )
     
```
# 83.saleStatistics  销售统计
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必须|
<br> |startTime|string|开始时间|可选|
<br> |endTime|string|结束时间|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br>### 返回信息:
```php
 success:
array (
    'status' => 0,
    'data' =>array (
    'total' => 29,
    'page' => 1,
    'limit' => 10,
    'goods_sale_num' => '202',
    'goods_sale_money' => '34911.30',
    'goods_sale_profit' => -159679.66,
    'service_sale_num' => '79',
    'service_sale_money' => '12650.83',
    'list' =>array (
    0 =>
    array (
    'date' => '2015-12-25',
    'total_sale_money' => '42.33',
    'total_orders' => '1',
    'goods_sale_num' => '1',
    'goods_sale_money' => '41.50',
    'goods_sale_profit' => 7,
    'service_sale_num' => '1',
    'service_sale_money' => '0.83',
    'total_profit' => 7.72,
    ),
    ),
    ),
    )
```
# 84.profitStatistics  利润统计
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必须|
<br> |startTime|string|开始时间|可选|
<br> |endTime|string|结束时间|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br> |export|int|是否导出|可选|
<br>### 返回信息:
```php
 success:
array (
    'status' => 0,
    'data' =>
    array (
    'total' => '308',
    'page' => 1,
    'limit' => 10,
    'list' =>
    array (
    0 =>
    array (
    'id' => '4957',
    'turnover' => '0.00',
    'clerk_commission' => '0.00',
    'profit' => '0.00',
    'create_time' => '2015-12-10',
    ),
    ),
    ),
    )
```
# 85.settlementStatistics  服务结算报表
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|生活馆商户id|必须|
<br> |startTime|string|开始时间|可选|
<br> |endTime|string|结束时间|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br> |export|int|是否导出|可选|
<br>### 返回信息:
```php
 success:
array (
    'status' => 0,
    'data' =>
    array (
    'page' => 1,
    'limit' => 20,
    'total' => '5',
    'list' =>
    array (
    0 =>
    array (
    'id' => '15623',
    'settlement_num' => '74',
    'settlement_money' => '7517.00',
    'create_time' => '2015-08-25',
    ),
    ),
    ),
    )
```
# 86.turnoverStatistics  营业额报表
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必须|
<br> |startTime|string|开始时间|可选|
<br> |endTime|string|结束时间|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br> |export|int|是否导出|可选|
<br>### 返回信息:
```php
 success:
  array (
    'page' => 1,
    'limit' => 20,
    'total' => '308',
    'list' =>
    array (
    0 =>
    array (
    'id' => '4957',
    'turnover' => '0.00',
    'pay_cash' => '0.00',
    'pay_card' => '0.00',
    'pay_balance' => '0.00',
    'pay_alipay' => '0.00',
    'pay_wechat' => '0.00',
    'create_time' => '2015-12-10',
    ),
    ),
    ),
    )
```
# 87.dealRecordsStatistics  会员交易记录
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必须|
<br> |startTime|string|开始时间|可选|
<br> |endTime|string|结束时间|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br> |export|int|是否导出|可选|
<br>### 返回信息:
```php
 success:
array (
    'status' => 0,
    'data' =>
    array (
    'total' => 38,
    'page' => 1,
    'limit' => 10,
    'list' =>
    array (
    0 =>
    array (
    'Date' => '2015-12-28',
    'Consume' => 0,
    'Recharge' => '692.00',
    'Balance' => '100127211.99',
    'ConsumeCnt' => 0,
    'RechargeCnt' => '3',
    ),
    ),
    ),
    )
```
# 88.commissionList 店员佣金报表
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必须|
<br> |startTime|string|开始时间|可选|
<br> |endTime|string|结束时间|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br> |export|int|是否导出|可选|
<br>### 返回信息:
```php
 success:
array (
    'status' => 0,
    'data' =>
    array (
    'page' => 1,
    'limit' => 10,
    'total' => 3,
    'list' =>
    array (
    0 =>
    array (
    'id' => '299',
    'clerk_name' => '加速的高发',
    'service_num' => '4',
    'service_money' => '0.00',
    'startTime' => '2015-11-29',
    'endTime' => '2015-12-29',
    ),
    ),
    ),
    )
```
# 89.voucherCheckList 服务验证记录
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必须|
<br> |verifyStartTime|string|验证开始时间|可选|
<br> |verifyEndTime|string|验证结束时间|可选|
<br> |settleStartTime|string|结算开始时间|可选|
<br> |settleEndTime|string|结算结束时间|可选|
<br> |settlement|int|结算状态|可选|
<br> |mobile|string|用户手机号|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br> |export|int|是否导出|可选|
<br>### 返回信息:
```php
 success:
array (
    'status' => 0,
    'data' =>
    array (
    'page' => 1,
    'limit' => 10,
    'total' => '2904',
    'list' =>
    array (
    0 =>
    array (
    'id' => '1370',
    'code' => '11369',
    'name' => '千航轩宠物',
    'mobile' => '18521521598',
    'create_time' => '1450752123',
    'use_time' => '1450752819',
    'goods_num' => '2',
    'verify_num' => '1',
    'city_name' => '上海',
    'discount_price' => '6.00',
    'business_price' => '6.00',
    'is_settle' => '0',
    'settle_time' => '0',
    'account_name' => '邱兰',
    'bank_name' => '光大银行',
    'bank_account' => '6226630601007171',
    ),
    ),
    ),
    )
```
# 90.stockStatistics  进货统计
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必须|
<br> |startTime|string|开始时间|可选|
<br> |endTime|string|结束时间|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br>### 返回信息:
```php
 success:
array(
    'status' => 0,
    'data' =>array (
    'total' => 36,
    'page' => 1,
    'limit' => 10,
    'all_num' => '92147',
    'all_price' => '4055163.67',
    'list' =>array (
    0 =>array (
    'date' => '2015-12-14',
    'total_price' => 240,
    'total_stocks' => 3,
    'total_order' => 1,
    'total_sku' => 1,
    ),
    ),
    ),
    )}
```
# 91.quickSearch 快速查询
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |key|string|关键字|可选|
<br> |bid|int|商户id|必填|
<br>### 返回信息:
```php
 success:

 fail:

```
# 92.saveOrder 出入库,盘点接口
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |op|int|操作人id|可选|
<br> |goods|string|商品列表(以逗号分割)|必填|
<br> |stocks|string|库存列表(以逗号分隔,出入库为出入库数量,盘点为盘点后的库存)|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
'status'=>1,'msg'=>'失败'
```
# 93.orderList  出库单/入库单/盘点单查询列表
     
### author: fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |type|int|类型|可选|
<br> |code|string|单号|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br>### 返回信息:
```php
 success:
array(
        'status'=>0,
        'data'=>array(
      ))
```
# 94.orderDetail 查询出入库,盘点单详情
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |oid|string|单号|必填|
<br>### 返回信息:
```php
 success:
array(
        'id' => '单子id',
        'orderCode' => '单子编号',
        'total_product' => '商品sku数',
        'total_stocks' => '商品库存总数',
        'create_time' => '单子创建时间',
        'remark' => '单子备注',
        'goods' = array(
            id => '商品id',
            code => '商品编号',
            pname => '商品名称',
            bname => '商品品牌',
            cname => '分类名称',
            stock => '商品库存',
        )
     )
```
# 95.addStockOrder  确认下单接口
     
### version:  1.0
     
### author:  unknown
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br> |strGoods|stirng|下单商品(购物车ID|进货数量,购物车ID|进货数量,)|必填|
<br> |mobile|string|用户电话|必填|
<br> |mobile|name|用户姓名|必填|
<br> |address|string|用户地址|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0, 'msg' => '成功')
```
# 96.purchaseOrderDetail 进货单详情
     
### version:  1.0
     
### author: @ fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |orderId|int|订单id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(
        'id'=>'订单id',
        'code'=>'订单编号',
        'total'=>'订单总金额',
        'status'=>'订单状态',
        'type'=>'订单类型',
        'goods'=>array(
                array(
                    'product_name'=>'商品名称',
                    'code'=>'商品编号',
                    'dicount_info'=>'优惠信息',
                    'stock_price_yuan'=>'进货价格',
                    'subtotal'=>'小计',
                ),
        )
     ))
```
# 97.confirmStock 确认收货页面详情
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|订单id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array(
        'id'=>'订单id',
        'code'=>'订单code',
        'product'=>array('product_id'=>'商品id','goods_num'=>'进货数量','stock_price'=>'进货价','real_goods_num'=>'实际进货数量',
            'real_stock_price'=>'实际进货价格',''
     )))
```
# 98.receiveConfirm
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |order_id|int|订单id|必填|
<br> |goods_id|array|商品id数组|必填|
<br> |real_goods_num|array|商品实际收货数量|必填|
<br> |real_stock_price|array|商品实际进货单价|必填|
<br> |uid|int|操作人id|必填|
<br> |bid|int|商户id|必填|
<br> |o2obid|int|生活馆商户id|必填|
<br>
# 99.receiveConfirms 批量确认收货
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |ids|string|订单id(逗号分隔)|必填|
<br> |bid|int|商户id|必填|
<br> |o2obid|int|生活馆商户id|可选|
<br> |operator|int|操作人id|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
array('status'=>1,'msg'=>'批量确认收货失败')
```
# 100.adjustStock 调整库存接口
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |merchantId|int|商户id|必填|
<br> |pid|int|商品id|必填|
<br> |stock|int|调整后库存值|必填|
<br> |reason|string|调整原因|可选|
<br> |operator|int|操作人id|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0)
 fail:
'status'=>1,'msg'=>'错误原因'
```
# 101.adjustThreshold 调整商品库存警戒值
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |merchantId|int|商户id|必填|
<br> |pid|int|商品id|必填|
<br> |on|int|是否开启库存预警|可选|
<br> |threshold|int|库存预警值|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0)
 fail:
array('status' => 1, 'msg' => '失败原因')
```
# 102.adjustPayPrice 调整商品售价
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |id|int|商品id|必填|
<br> |pay_price|float|商品售价|必填|
<br>### 返回信息:
```php
 success:
array('status' => 0)
 fail:
array('status' => 1, 'msg' => '失败原因')
```
# 103.Inventorylist 商品库存列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |code|string|商品编号|可选|
<br> |name|string|商品名称|可选|
<br> |category|int|商品分类id|可选|
<br> |brand|int|商品品牌id|可选|
<br> |stockStart|int|库存区间|可选|
<br> |stockEnd|int|库存区间|可选|
<br> |warningStock|int|预警库存|可选|
<br> |export|int|是否导出|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br>### 返回信息:
```php
 success:

    array (
    'status' => 0,
    'data' =>
    array (
    'limit' => 10,
    'page' => 1,
    'total' => '25',
    'total_stock' => '14458',
    'list' =>
    array (
    0 =>
    array (
    'sid' => '748',
    'last_time' => '上次更新时间',
    'pid' => '317',
    'name' => '星记消防栓FP造型玩具组合小号',
    'code' => '873199000508',
    'top_category_id' => '1',
    'standard' => '',
    'stock' => '320',
    'stock_price' => '31.00',
    'brand_id' => '1243',
    'channel_id' => '0',
    'top_category' => '犬',
    'brand' => NULL,
    'channel' => NULL,
    ),
    ),
    ),
    )
 fail:
array('status'=>1,'msg'=>'未查询到信息')
```
# 104.getStorageType  获取出入库类型
     
### 返回信息:
```php
 success:
array(
    1=>'出库单',
    2=>'入库单',
    3=>'盘点单',
    4=>'销售出库单',
    5=>'期初入库单',
    6=>'采购入库单'
    )
```
# 105.goodsStockRecord 商品库存变更记录
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |pid|int|商品id|必填|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br>### 返回信息:
```php
 success:

    array(array (
    'status' => 0,
    'data' =>
    array(
    'id' => '285',
    'name' => '星记磨牙球TB大号',
    'code' => '1111',
    'stock' => '19',
    'warning_stock' => '2',
    'last_time' => '1448964731',
    'total' => '2',
    'recordList' =>
    array (
    0 =>
    array (
    'number' => '198',
    'create_time' => '1449025513',
    'code' => '1512023147006',
    'status' => '0',
    'type' => '3',
    ),
    1 =>
    array (
    'number' => '2',
    'create_time' => '1448964731',
    'code' => '1512015147002',
    'status' => '1',
    'type' => '5',
    ),
    ),
    ),
    ))
 fail:
array('status'=>1,'msg'=>'未查询到商品信息')
```
# 106.hasWarningProduct 是否有库存告急商品
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |businessId|int|商户id|必填|
<br>### 返回信息:
```php
 success:
array('status'=>0,'data'=>array('has'=>true/false),'msg'=>'有库存告急/无库存告急')
```
# 107.stockList  进货单列表
     
### version:  1.0
     
### author:  fangyong
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |code|string|商品编号|可选|
<br> |name|string|商品名称|可选|
<br> |brand|id|商品品牌|可选|
<br> |category|id|商品分类|可选|
<br> |startTime|string|下单时间|可选|
<br> |endTime|string|下单时间|可选|
<br> |isConfirm|int|是否确认收货|可选|
<br> |page|int|页码|可选|
<br> |limit|int|分页数量|可选|
<br>### 返回信息:
```php
 success:
array('status'=>0,'total'=>'总条数','data'=>array())
 fail:
array('status'=>1,'msg'=>'未查询到相关数据')
```
# 108.purchaseList  进货列表
     
### 参数列表:
 |    参数名    | 参数类型 |      参数说明      | 是否必须 |
<br> |-------------|:-------:|:-----------------:|---------|
<br> |bid|int|商户id|必填|
<br> |||||
<br>
