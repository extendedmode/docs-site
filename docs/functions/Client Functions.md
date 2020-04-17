<h1>Exclusive Functions</h1>
Functions exclusive to the extendedmode framework

!!! Note
    For these functions to work you must be using the extendedmode method of importing functions.
	To do this simply add `shared_script '@extendedmode/imports.lua'` to your fxmanifest.lua.

## ExM.Game.PlayAnim
```
ExM.Game.PlayAnim(animDict, animName, upperbodyOnly, duration)
```

This function is a quick and easy way to play any animation you want without having to request animation dictionaries or specify a heap of parameters.
<h3>Parameters</h3>

| Argument 		| Data Type | Optional 	| Default Value 		| Description |
| ------------- | --------- | ----------| --------------------- | ----------- |
| animDict 		| string 	| No 		| - 					| The animation dictionary |
| animName 		| string 	| No 		| - 					| The animation in the dictionary to play |
| upperbodyOnly | boolean 	| Yes 		| false 				| If you want the animation to only affect the upperbody |
| duration 		| integer 	| Yes 		| -1 (full animation) 	| Duration in ms you want the animation to run for |

<h3>Example</h3>
```
ExM.Game.PlayAnim("mini@sprunk", "plyr_buy_drink_pt1", false, 1500)
```

------

## ExM.Game.CreatePed
```
ExM.Game.CreatePed(pedModel, pedCoords, isNetworked, pedType)
```

This function is a quick and easy way to create a ped without having to request models or anything, you can choose whether or not to store the ped in a variable or not.
<h3>Parameters</h3>

| Argument 		| Data Type | Optional 	| Default Value 		| Description |
| ------------- | --------- | ----------| --------------------- | ----------- |
| pedModel 		| hash	 	| No 		| - 					| The model of the ped you want to spawn |
| pedCoords 	| vector	| No 		| - 					| You can use a vector3 or vector4 here, if only using a vector3 the heading will default to 0.0 |
| isNetworked 	| boolean 	| Yes 		| false 				| If you want the ped to be networked or not |
| pedType 		| integer 	| Yes 		| 4 (PED_TYPE_CIVMALE)	| The type of ped you want to use. [List of Ped Types](https://hastebin.com/mecuguxipo) |

<h3>Example</h3>
```
local coords = GetEntityCoords(PlayerPedId())
local ped = ExM.Game.CreatePed(`a_m_m_acult_01`, vec4(coords.xyz, 180.0), true, 27)
```

------