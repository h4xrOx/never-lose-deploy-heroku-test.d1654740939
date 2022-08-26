
# cheat

## ESP API

{% hint style="info" %}
You can create your own ESP elements. More info can be found [here](../other/espapi.md).
{% endhint %}

## Menu API

{% hint style="info" %}
You can create your menu elements. More info can be found [here](../other/menuapi.md).
{% endhint %}

## Functions

## RegisterCallback

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| event\_name | string | Event names |
| callback | function | Callback |

{% hint style="info" %}
You can view callbacks list [here](../other/callbacks.md).
{% endhint %}

```lua
cheat.RegisterCallback("draw", function()
    g_Render:Text("Hello world, it's me", Vector2.new(10.0, 15.0), Color.new(1.0, 1.0, 1.0), 16)
end)
```

## FireBullet

### Simulates bullet with wall penetrating

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| attacker | C\_BasePlayer | Attacker |
| start | Vector | Simluation start pos |
| end | Vector | Simluation end pos |

### Return value:

| Name | Type | 
| :--- | :--- |
| Fire Bullet Info | firebullet_t | 

```lua
local trace = cheat.FireBullet(player, Vector.new(0.0, 0.0, 0.0), Vector.new(1.0, 1.0, 1.0))
print(trace.damage)
```

## AngleToForward

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| ang | QAngle | Input angle |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| vec | Vector | Output vector |

```lua
local vec = cheat.AngleToForward(QAngle.new())
```

## VectorToAngle

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| vec | Vector | Input vector |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| ang | QAngle | Output angle |

```lua
local ang = cheat.VectorToAngle(Vector.new(100, 100, 100))
```

## IsMenuVisible

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | bool | Is menu opened or not |

```lua
local is_visible = cheat.IsMenuVisible()
```

## GetMousePos

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | Vector2 | Mouse position on screen |

```lua
local mouse_pos = cheat.GetMousePos()
```

## IsKeyDown

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| key | int | Virtual key code |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | bool | Is key down |

{% hint style="info" %}
You can find all virtual keys [here](https://docs.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes)
{% endhint %}

```lua
local is_key_pressed = cheat.IsKeyDown(0x1)
```

## GetCheatUserName

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | Neverlose's account username |

```lua
local username = cheat.GetCheatUserName()
```

## GetBinds

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| binds | table (`ActiveBind`s array)| Binds |

```lua
local binds = cheat.GetBinds()
print("Name", "isActive", "Value")
for i = 1, #binds do
    print(binds[i]:GetName(), binds[i]:IsActive(), binds[i]:GetValue())
end
```

## AddEvent

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | Event name |

```lua
cheat.AddEvent("Greetings from neverlose.cc!")
```

## AddNotify

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| title | string | Notification title |
| name | string | Notification name |

```lua
cheat.AddNotify("neverlose.cc", "Greetings from elleqt!")
```
# antiaim

{% hint style="info" %}
Override* functions can be called only from pre-createmove [callbacks](../other/callbacks.md) (`pre_prediction`, `prediction`).
{% endhint %}

## Functions

## OverrideInverter

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | bool | A new value for inverter |

```lua
antiaim.OverrideInverter(false)
```

## OverrideLimit

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | float | A new desync limit value (0 - 58) |

```lua
antiaim.OverrideLimit(30)
```

## OverrideYawOffset

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | float | A new yaw offset value (-180 - 180) |

```lua
antiaim.OverrideYawOffset(90)
```

## OverrideLBYOffset

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | float | A new lby offset value (-58 - 58) |

```lua
antiaim.OverrideLBYOffset(58)
```

## OverridePitch

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | float | A new pitch value |

```lua
antiaim.OverridePitch(90) -- UP
```

## GetInverterState

### Return value:

| Type | Description |
| :--- | :--- |
| bool | Current inverter state |

```lua
local inverter_state = antiaim.GetInverterState()
```

## GetMinDesyncDelta

### Return value:

| Type | Description |
| :--- | :--- |
| float | Minimal desync delta |

```lua
local min_desync_delta = antiaim.GetMinDesyncDelta()
```

## GetMaxDesyncDelta

### Return value:

| Type | Description |
| :--- | :--- |
| float | Max desync delta |

```lua
local max_desync_delta = antiaim.GetMaxDesyncDelta()
```

## GetFakeRotation

### Return value:

| Type | Description |
| :--- | :--- |
| float | Fake rotation |

```lua
local desync_rotation = antiaim.GetFakeRotation()
```

## OverrideDesyncOnShot

### Parameters:

| Type | Description |
| :--- | :--- |
| int | 0 - disable override, 1 - left, 2 - right, 3 - overlap on shot with fake, 4 - opposite to fake |

```lua
antiaim.OverrideDesyncOnShot(4) 
```

## GetCurrentRealRotation

### Return value:

| Type | Description |
| :--- | :--- |
| float | Real rotation |

```lua
local real_rotation = antiaim.GetCurrentRealRotation()
```
# exploits

## Functions

## GetCharge

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | float | Charge fraction |

```lua
local chrg = exploits.GetCharge()
```

## AllowCharge

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | bool | true - block charge, false - allow charge |

```lua
exploits.AllowCharge(false)
```

## ForceTeleport

### Teleports local player if doubletap is charged

```lua
exploits.ForceTeleport()
```

## ForceCharge

### Force doubletap to charge

```lua
exploits.ForceCharge()
```

## OverrideDoubleTapSpeed

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| speed | int | How many ticks doubletap will speed up |

```lua
exploits.OverrideDoubleTapSpeed(13) -- Default value
```
# fakelag

## Functions

## Choking

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | bool | Is chocking packet |

```lua
local chocking = fakelag.Choking()
```

## ForceSend

### Choke this tick, and send packet on next tick.

```lua
fakelag.ForceSend()
```

## SentPackets

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | int | How many packets sent in row. |

```lua
local sent_packets_num = fakelag.SentPackets()
```

## SetState

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| state | bool | Set packet state False - choke packet True - send packet |

```lua
fakelag.SetState(false)
```
# http

## Functions

## Get

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| url | string | URL link |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| content | string | Content of provided URL |

```lua
local google_content = http.Get("https://google.com")
```

## Post

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| url | string | URL link |
| params | string | POST Parameters |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| content | string | Content of provided URL |

```lua
local google_content = http.Post("https://google.com", "somedata=somevalue")
```

## GetAsync

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| url | string | URL link |
| callback | function | - |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| content | string | Content of provided URL |

```lua
http.GetAsync("https://google.com", function(url_content)
  print(url_content)
end)
```

## PostAsync

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| url | string | URL link |
| params | string | POST Parameters |
| callback | function | - |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| content | string | Content of provided URL |

```lua
http.PostAsync("https://google.com", "somedata=somevalue", function(url_content)
  print(url_content)
end)
```

# ragebot

{% hint style="info" %}
Hitboxes:
```
	0. head
	1. neck 
	2. pelvis 
	3. stomach 
	4. lower chest 
	5. chest 
	6. upper chest 
	7. right thigh 
	8. left thigh 
	9. right calf 
	10. left calf 
	11. right foot 
	12. left foot 
	13. right hand 
	14. left hand 
	15. right upper arm 
	16. right forearm 
	17. left upper arm 
	18. left forearm
```
{% endhint %}

## Functions

## OverrideMinDamage

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Entity index |
| value | int | New mindamage |

```lua
ragebot.OverrideMinDamage(1, 10)
```

## OverrideHitchance

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Entity index |
| value | int | New hitchance |

```lua
ragebot.OverrideHitchance(1, 10)
```

## ForceSafety

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Entity index |

```lua
ragebot.ForceSafety(1)
```

## SetTargetPriority

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Entity index |
| priority | int | Arbitrary numerical priority value - higher value = higher priority |

```lua
ragebot.SetTargetPriority(1, 100)
```

## SetHitboxPriority

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Entity index |
| hitbox | int | Hitbox index |
| priority | int | Arbitrary numerical priority value - higher value = higher priority |

```lua
ragebot.SetHitboxPriority(1, 0, 100)
```

## ForceHitboxSafety

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Entity index |
| hitbox | int | Hitbox index |

```lua
ragebot.ForceHitboxSafety(1, 0)
```

## EnableHitbox

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Entity index |
| hitbox | int | Hitbox index |
| state | bool | Hitbox state |

```lua
ragebot.EnableHitbox(1, 0, false)
```

## EnableMultipoints

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Entity index |
| hitbox | int | Hitbox index |
| state | bool | Multipoint state |

```lua
ragebot.EnableMultipoints(1, 0, false)
```

## IgnoreTarget

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | Entity index |

```lua
ragebot.IgnoreTarget(1)
```
# utils

## Functions

## CreateInterface

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| module\_name | string | Module name |
| interface\_name | string | Interface name |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | void\* | Interface |

```lua
local game_movement = utils.CreateInterface("client.dll", "GameMovement001")
```

## PatternScan

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| module\_name | string | Module name |
| pattern | string | IDA-like pattern |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | void\* | Interface |

```lua
local clantag_change_fn = utils.PatternScan("engine.dll", "53 56 57 8B DA 8B F9 FF 15")
```

## RandomFloat

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| min | float | Min value |
| max | float | Max value |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | float | Random float from min to max |

```lua
local rnd_float = utils.RandomFloat(0.0, 20.0)
```

## RandomInt

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| min | int | Min value |
| max | int | Max value |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | int | Random int from min to max |

```lua
local rnd_int = utils.RandomInt(0, 20)
```

## RandomSeed

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| seed | int | Seed value |

```lua
utils.RandomSeed(cmd.random_seed)
```

## RegisterConVar

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | Console var name |
| value | string | Console var default value |
| flags | int | [Convar flags](https://gist.github.com/es3n1n/fe2051a24ffef32a8219823e7ef69b05#file-e_cvar_flags-lua-L3) |
| description | string | Console var description |
| callback | function | Callback |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | ConVar | Registered console var instance |

```lua
local cvar = utils.RegisterConVar('meme_var', '1', 8, 'Testing stuff', function(cvar, old, new)
	print('meme_var value was changed from ' .. old .. ' to ' .. new)
end)
print(cvar:GetString())
```

## RegisterConCommand

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | Console command name |
| flags | int | [Convar flags](https://gist.github.com/es3n1n/fe2051a24ffef32a8219823e7ef69b05#file-e_cvar_flags-lua-L3) |
| description | string | Console command description |
| callback | function | Callback |

### Return value:

| Name | Type | Description |
| :--- | :--- | :--- |
| value | ConVar | Registered console command instance |

```lua
local cmd = utils.RegisterConCommand('meme_cmd', 8, 'Testing stuff', function(cvar)
	print("it's wednesday, my dudes")
end)
```

## UnixTime

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| epoch | int | Unix time |

```lua
local unx = utils.UnixTime()
```







