<p align="center">
    <img src="https://github.com/RimWorldProjectArmory/ProjectArmory/blob/master/extras/assets/logo/logo.png?raw=true" width="480">
</p>
This mod adds new weapons to the RimWorld Universe from different games, movies and real world periods from the Victorian era to modern day. We try to match the function and the graphic to be ad close to the vanilla weapons as possible and make them as balanced as possible with a unique twist.

## Weapon calculation formulas:

| Weapon Class      | Formula                                     |Base Weapon      | Note            |
|-------------------|---------------------------------------------|-----------------|-----------------|
|Assault Rifles     | `[Muzzle Energy] / 254.57`                  |                 |                 |
|Pistols            | `[Muzzle Energy] / 46.66`                   |                 |                 |
|Shotguns           | `( [Muzzle Energy] / 180.87 ) / 1.5 + 10`   |                 |                 |
|PDW                | `[Muzzle Energy] / 105`                     |                 | def. in wiki    |
|SMG                | `( [Muzzle Energy] / 42 ) / 2 + 5`          |                 |                 |
|Rifles             | `[Muzzle Energy] / 222.97`                  |                 |                 |
|Sniper Rifle       | `[Muzzle Energy] / 90.525`                  |                 |                 |
|Sniper Rifle AT    | `[Muzzle Energy] / 90.525 / 10 + 40`        |                 | above 9000 J    |

To calculate the damage of a weapon you will have to use wiki, and these parameters which are best illustrated in the table below. But before that, here are some definitions:

Tested Barrel Length - Is the parameter which is stated on wiki page of the caliber you're looking at, below the small table of test info on bullets, written in cursive like so: Test barrel length: Tests 1,2&3: 150mm(5.91in) / Tests 4&5: 118mm(4.65in). Barrel is measured in mm in our calculations, if length in mm is not stated, convert it to mm from inches(and round to closest mm value). If tested barrel length is not stated at all, use the test values which correspond the closest with the muzzle velocity of the weapon you are setting the damage for, and set the tested barrel length to the same value as the actual barrel length.

Tested Energy - Is the parameter which is written in that table. You are free to choose whatever type of projectile or bullet you want from that table, but it has to correspond to the chosen velocity. Energy is measured in Joules. 

Tested Velocity - Is the parameter which is written in that table. It is highly recommended that the velocity choosen from the table has to be slower than muzzle velocity if the tested barrel is shorter than your weapon's barrel. If the tested barrel is longer than your weapon's barrel, pick the velocity which is faster than your weapon's muzzle velocity.

Barrel Length - Is the parameter which is given on the right side on wiki page for your chosen weapon. If it is not stated, try using inderect sources to find the barrel length of the given weapon. 

Muzzle Velocity - Is the parameter which is given on the right side on wiki page for your chosen weapon. If it is not stated, use cartridge test parameters. 

Muzzle Energy - Is the parameter which you will have to calculate using this formula: 

``` c++
[Muzzle Energy] = [Barrel length] / [Tested Barrel Length] * ( [Tested Energy] / [Tested Velocity] * [Muzzle Velocity] )
```

Here are some exsample values for Assault Rifles:

|                       | M16       | AK47    |  G36    |MadeUp   |
|-----------------------|-----------|---------|---------|---------|
| Tested Barrel Length  | `508`     | `415`   | `508`   | `500`   |
| Tested Velocity       | `940`     | `730`   | `940`   | `835`   |
| Tested Energy         | `1767`    | `2108`  | `1767`  | `2500`  |
| Barrel Length         | `508`     | `415`   | `480`   | `402`   |
| Muzzle Velocity       | `948`     | `715`   | `920`   | `765`   |
|                       |           |         |         |         |
| Muzzle Energy         | `1782`    | `2064`  | `1634`  | `1841`  |
|                       |           |         |         |         |
| `damageAmountBase`    | `7.0`     | `8.1`   |  `6.4`  | `7.2`   |

Damage for a assult rifle whould be: `[damageAmountBase] = [Muzzle Energy] / 254.57`

For practice try calculating the damage of MadeUp weapon given the parameters, and then If you're up to the task, try calculating the damage(and finding the info about the weapon) of IMI Galil. 

### Forumla for weapon range calculation:
``` c++
range = ( ( ( [Muzzle Velocity] / 20) + ( [Barrel Length] / 20 ) ) / 4 ) + [Adjustment Value]
```

| Weapon Class      | Adjustment Value  |Base Weapon      | Note              |
|-------------------|-------------------|-----------------|-------------------|
|Assault Rifles     | `16.2`            |                 |                   |
|Pistols            | `20.4`            |                 |                   |
|Shotguns           |  `1.7`            |                 |                   |
|PDW                | ``                |                 |                   |
|SMG                | `16.7`            |                 |                   |
|Rifles             | `21.6`            |                 |                   |
|Sniper Rifle       | `28.5`            |                 |                   |
|Sniper Rifle AT    | `28.5`            |                 |                   |
|Lite Mashine Gun   | `9.9`             |                 |                   |
|Heavy Mashine Gun  | `10.0`            |                 |                   |


<p align="center"><a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">Project Armory</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/RimWorldProjectArmory" property="cc:attributionName" rel="cc:attributionURL">Project Armory Development Team</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>.<br />Based on a work at <a xmlns:dct="http://purl.org/dc/terms/" href="http://rimworldgame.com/" rel="dct:source">http://rimworldgame.com/</a>.</p>
