# PUBG API Developer Resources

Art assets and data dictionaries for use with the PUBG API.

## Assets

The `assets` folder contains art assets for equipment, weapons, and more. Assets for data found in the telemetry will have a similar file name. For example, `Item_Attach_Weapon_Lower_AngledForeGrip_C` in the telemetry will match up to `Item_Attach_Weapon_Lower_AngledForeGrip.png`.

## Dictionaries

The `dictionaries` folder contains files that map some of the longer and confusing data names from the telemetry to shorter human-readable versions. The name of each mapping file corresponds to a key in the telemetry data. Each key in the mapping files is a possible value for the key corresponding to the file name in the telemetry data. The value of each key in the mapping files is the shortened human-readable name for that value in the telemetry data. For example:

Here is an example line from the telemetry data:

```
"itemId": "Item_Attach_Weapon_Stock_SniperRifle_CheekPad_C"
```

We look at the key here to determine the mapping file. In this case, it is `itemId`, so we need to look in `itemId.json`. Within this mapping file, there is the following entry:

```
"Item_Attach_Weapon_Stock_SniperRifle_CheekPad_C": "Sniper Rifle Cheek Pad"
```

Here we find that the *pretty* name for `Item_Attach_Weapon_Stock_SniperRifle_CheekPad_C` is "Sniper Rifle Cheek Pad".

**NOTE**: Not all of the telemetry data will have associated mapping files.

## Enums

The `enums` folder contains files with an array of possible values for the telemetry data kay associated with each filename. For example:

Here is a basic schema for the item object found throughout the telemetry data:

```
{
  "itemId": string,
  "stackCount": int,
  "category": string,
  "subCategory": string,
  "attachedItems": [ItemId, ...]
}
```

Similar to the how dictionary works for values of `ItemId`, we can look up all of the possible values for `category` and `subcategory` in `category.json` and `subcategory.json` respectively. The difference here is that the possible values do not need mapping because their meanings are straightforward.

## Community Contributions

Community contributions and feedback are welcome! Please feel free to submit an issue if there is something missing or not quite right, and we will take a look as soon as we are able.
