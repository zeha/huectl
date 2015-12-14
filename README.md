# huectl quickstart

## install

```
$ brew install python3
$ pip install -r requirements.txt
```

- or -  

```
$ apt-get install python3 python3-requests
```

## basic usage

Initial setup and list lights:

```
$ huectl
Press link button on bridge 192.168.0.100 now.......

1     Bedroom 1               Extended color light      {'reachable': True, 'sat': 254, 'xy': [0.305, 0.3126], 'effect': 'none', 'on': False, 'bri': 254, 'alert': 'none', 'hue': 34840, 'colormode': 'xy', 'ct': 153}
3     floor lamp              Extended color light      {'reachable': True, 'sat': 254, 'xy': [0.305, 0.3126], 'effect': 'none', 'on': False, 'bri': 254, 'alert': 'none', 'hue': 34840, 'colormode': 'xy', 'ct': 153}
2     Bedroom 2               Extended color light      {'reachable': True, 'sat': 254, 'xy': [0.305, 0.3126], 'effect': 'none', 'on': False, 'bri': 254, 'alert': 'none', 'hue': 34840, 'colormode': 'xy', 'ct': 153}
```

Turn a light on:

```
$ huectl on 2
[{'success': {'/lights/2/state/on': True}}]
```

Back off:

```
$ huectl off 2
[{'success': {'/lights/2/state/on': False}}]
```

Dim a light:

```
$ huectl dim 3 30
[{'success': {'/lights/3/state/on': True}}, {'success': {'/lights/3/state/bri': 127}}]
```


## scenes

List scenes:

```
$ huectl scenes
9b91fe11f-on-0  Deep sea on 0                  1 2 3
ac637e2f0-on-0  Relax on 0                     1 2 3
OFF-TAP-1       Tap scene 1                    1 2 3
TAP-2           Tap scene 2                    1 2 3
TAP-3           Tap scene 3                    1 2 3
TAP-4           Tap scene 4                    1 2 3
```

Activate scene `TAP-2`:

```
$ huectl scene TAP-2
[{'success': {'/groups/0/action/scene': 'TAP-2'}}]
```

Get details (lights, lightstates) for `TAP-2`:

```
$ huectl scene-detail TAP-2
ID:       TAP-2
Name:     Tap scene 2
Lights:   1 2 3
Flags:    recycle v1
```
(Lightstates are not stored in the bridge for v1 scenes.)


## sensors

List sensors:

```
$ huectl sensors
1     Daylight                       Daylight        {'lastupdated': 'none', 'daylight': None}
2     Hue tap switch 1               ZGPSwitch       {'lastupdated': 'none', 'buttonevent': None}
3     Hue dimmer switch 1            ZLLSwitch       {'lastupdated': 'none', 'buttonevent': None}
```
