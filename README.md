# ZhiMqtt

Generic MQTT Component for HomeAssistant

基于 MQTT Swicth 的扩展开关，支持以下功能：

- 支持 icon_template 配置，可以使用 Jinja 脚本运算出不同的图标。
- 支持 original_state 属性。

## 1. 安装准备

把 `zhimqtt` 放入 `custom_components`。

## 2. 配置方法

参见 [我的 Home Assistant 配置](https://github.com/Yonsm/.homeassistant) 中 [configuration.yaml](https://github.com/Yonsm/.homeassistant/blob/main/configuration.yaml)

```yaml
switch:
  - platform: zhimqtt
    name: 书房音箱
    state_topic: NodeMCU2/relay/0
    command_topic: NodeMCU2/relay/0/set
    availability_topic: NodeMCU2/status
    value_template: '{% if value == "关闭" %}OFF{% else %}ON{% endif %}'
    icon_template: '{% if value == "关闭" %}mdi:speaker-off{% elif value == "蓝牙" %}mdi:speaker-bluetooth{% elif value == "光纤" %}mdi:speaker-wireless{% elif value == "优盘" %}mdi:usb{% elif value == "辅助" %}mdi:video-input-component{% else %}mdi:speaker{% endif %}'
```

## 3. 参考

- [Yonsm.NET](https://yonsm.github.io)
- [Yonsm's .homeassistant](https://github.com/Yonsm/.homeassistant)
