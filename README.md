# Notifications

![Notifications mindmap](/images/mindmap.png?raw=true "Notifications mindmap")

Удобная и дешевая доставка коротких сообщений разнородным группам пользователей. Кого-то нет вконтакте, кто-то любит телеграм, у кого-то все контакты в вайбере. Notifications - универсальный абстрактный канал для доставки сообщения любому пользователю.

## Каналы

* Telegram
* Email
* Viber
* VK
* WhatsApp
* Facebook

## Как это может выглядеть в коде

```ruby
contact = Contact.new nick: 'Dick', telegram: '79991112233', email: 'contact@example.com', default_channel: :telegram
contact = Contact.new nick: 'Dick', channel: 'telegram:79991112233'
contact = Contact.new nick: 'Dick', channel: :telegram, uid: '79991112233'
contact.tag_list = 'party, metro_alerts, big sales'
contact.owner = current_user

some_contact.send(text)
some_contact.send(text, through: :email)
some_contact.send_through_all_channels!(text)
some_tag.send(text)

Channel::Telegram.send some_contact.telegram, text
```

## Публичные расслыки

Пользователи могут создавать публичные расслыки, например, "Вечеринки от Антошки", "Скидки в Летуаль", etc.

## Банки и смс

* http://siliconrus.com/2015/02/push-is-in-sms-is-out/
* http://top.rbc.ru/own_business/25/03/2015/55112f499a7947727d498660
