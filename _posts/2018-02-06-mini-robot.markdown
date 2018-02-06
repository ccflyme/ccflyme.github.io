---
layout:     post
title:      "Python写个迷你聊天机器人 | 生成器的高级用法"
subtitle:   ""
date:       2018-02-06
author:     "Tesla9527"
header-img: "img/post-bg-alitrip.jpg"
catalog:    false
tags:
    - Python
---
>本文转载自微信公众号菜鸟学Python，作者：xinxin。
```python
def chat_robot():
    res = ''
    while True:
        receive = yield res
        if 'hi' in receive or 'hello' in receive:
            res = 'Ni Hao'
        elif 'name' in receive:
            res = 'I am Tom'
        elif 'age' in receive or 'old' in receive:
            res = '10 years old'
        elif 'gender' in receive:
            res = 'Boy'
        elif 'from' in receive or 'where' in receive:
            res = 'China'
        elif 'height' in receive:
            res = 'My height is 173cm'
        elif 'weight' in receive:
            res = 'My weight is 70kg'
        elif 'hobby' in receive:
            res = 'Watching movie'
        elif receive == 'help':
            res = 'input key word such as: hi/name/age/old/gender/help/bye/q'
        elif 'bye' in receive:
            res = 'Bye bye, see u na la'
        else:
            res = "Sorry, I can't understand your input:{}. You can type help.".format(receive)


Chat = chat_robot()
next(Chat)
while True:
    human_input = input('Please input:')
    if human_input in ['Q', 'q']:
        print('Robot exit...')
        break
    response = Chat.send(human_input)
    print('Robot: {}'.format(response))
    if 'Bye bye' in response:
        break
Chat.close()
```
