# description
Grab ticket for Damai in automatic


## env
1. python 3.6(或以上版本)
2. chromedriver.exe(需放在chrome目录下)
3. chrome


## 参数设置
在config.json中输入相应配置信息，具体说明如下：

    date: 日期选择

    sess: 场次优先级列表

    price: 票价优先级，如本例中共有三档票价，根据下表，则优先选择1，再选择3；也可以仅设置1个。

    real_name: [1,2], 实名者序号，根据序号共选择两位实名者，根据序号，也可仅选择一位
 
    driver_path:浏览器驱动地址

    nick_name: 用户在大麦网的昵称，用于验证登录是否成功

    ticket_num: 购买票数

    damai_url: https://www.damai.cn, 大麦网官网网址

    target_url: https://detail.damai.cn/item.htm?id=607865020360, 具体url, 例如: 周杰伦2023嘉年华世界巡回演唱会--海口站


## 说明

部分门票需要选择城市，只需选择相应城市后将其网址复制到config.json文件的target_url参数。

根据需要选择的场次和票价分别修改config.json文件中的sess和price参数。

查看购票须知中实名制一栏，若无需实名制则config.json文件中的real_name参数不需要填写（即为[]）；若每笔订单只需一个证件号则real_name参数只需选择一个；若每张门票需要一个证件号，则real_name参数根据需购票数量进行相应添加。

若是首次登录，根据终端输出的提示，依次点击登录、扫码登录，代码将自动保存cookie文件（cookie.pkl）

使用前请将待抢票者的姓名、手机、地址设为默认。

配置完成后执行python damai_ticket.py即可,注意观察控制台输出。

本代码为保证抢票顺利，设置循环直到抢票成功才退出循环，若中途需要退出程序请直接终止程序。