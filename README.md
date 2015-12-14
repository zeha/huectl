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

## usage

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
