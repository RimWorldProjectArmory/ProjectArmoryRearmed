<p align="center">
    <img src="https://github.com/RimWorldProjectArmory/ProjectArmory/blob/master/extras/assets/logo/logo.png?raw=true" width="480">
</p>
This mod adds new weapons to the RimWorld Universe from different games, movies and real world periods from the Victorian era to modern day. We try to match the function and the graphic to be ad close to the vanilla weapons as possible and make them as balanced as possible with a unique twist.

## Weapon calculation formulas:

### Forumla for weapon damage calculation:
``` c++
damageAmountBase = ( ( [Energy] * 2 ) + ( [BarrelLeangth] + [MuzzleVelocity] - 600 ) / 1000 ) + [Adjustment Value]
```
| Weapon Class    | Adjustment Value    |
|-----------------|---------------------|
| Assault Rifles  | `2,6`               |

### Forumla for weapon range calculation:
``` c++
range = ( ( [Velocity] / 20) + ( [Barrel Length] / 20 ) / 4 ) + [Adjustment Value]
```
| Weapon Class    | Adjustment Value    |
|-----------------|---------------------|
| Assault Rifles  | `16.2`              |
| HMG             | `10.0`              |
| LMG             | `9.9`               |
| P               | `20.4`              |
| R               | `21.6`              |
| S               | `1.7`               |
| HSMG            |   	                |
| SMG             | `16.7`              |
| Sniper Rifles   | `28.5`              |

<p align="center"><a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">Project Armory</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/RimWorldProjectArmory" property="cc:attributionName" rel="cc:attributionURL">Project Armory Development Team</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>.<br />Based on a work at <a xmlns:dct="http://purl.org/dc/terms/" href="https://github.com/RimWorldProjectArmory" rel="dct:source">https://github.com/RimWorldProjectArmory</a>.</p>