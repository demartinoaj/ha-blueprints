# ha-blueprints
Collection of Home Assistant Blueprints I've created

## Pseudo Light Switch
  Virtually link A Zigbee2MQTT Switch to a Light entity, only using button press events to control the light.

The purpose of this blueprint is to provide a "smart bulb mode" for a Z2M connected ZigBee switch that doesn’t support it natively. I wanted to bind my Wi-Fi smart bulbs to my ZigBee switches in Home Assistant, but I found that my [Enbrighten](https://www.zigbee2mqtt.io/devices/43076.html) switches didn't properly report brightness in Home Assistant without a real load attached. So, I couldn't just have the switch entity shadow the light entity. I got around this by using the switch event sensor generated by Z2M and mapping the type of button press to my desired behavior.

My switches only supported on/off and brightness_move_up/down events, so double tap events will not register in this blueprint.
