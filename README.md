# TP TRADING PORT

## Development API Exports

When triggered, it opens the trading port NUI.

```lua
exports.tp_trading_port:OpenTradingNUI() 
```

-- Get Player Data
```lua
-- @param data.Level
-- @param data.LevelExperience
-- @param data.HasOrderPickup
-- @param data.IsBusy
-- @param data.CurrentDay
-- @param data.CurrentMonth

exports.tp_trading_port:GetPlayerData() -- returns a table.
```

If the player is nearby to the trading port office location.

```lua
exports.tp_trading_port:IsNearbyOfficeLocation() -- boolean
```

If the player is doing pickup order process

```lua
exports.tp_trading_port:IsInOrderPickup() -- boolean
```

## Countries Registration (Manual changes)


- 1. To create a new country (that does not exist), first, you go in the `config.lua` file and register it on `Config.Countries`, we gonna call this country as Turkiye.

Example:

```lua

  ['turkiye'] = { -- @param ID: (COUNTRY NAME)
    Label = 'Turkiye', Weight = 15000, WeightLabel = '15KG', 
    FlagImageUrl  = 'turkiye.png', -- the background image for the flag.
    PhotoImageUrl = 'turkiye.jpg', -- the background image for displaying the country image on the top.
  },

```

- 2. We register the country on `Config.CountryProducts`, this section is for buying products from this country.
 
Example:

```lua
Config.CountryProducts = {

  ['greece'] = { -- DEFAULT
    {item = "exampleItemName",   label = "example", type = "item",   currency = 0, cost = 1, weight = 300, maxQuantity = 100, requiredLevel = 1, givenExperience = 10},
  },

  ['italy'] = { -- DEFAULT
    {item = "exampleItemName",   label = "example", type = "item",   currency = 0, cost = 1, weight = 300, maxQuantity = 100, requiredLevel = 1, givenExperience = 10},
  },

  -- ... (!) TURKIYE BELOW ! NEW!
  ['turkiye'] = {
    {item = "exampleItemName",   label = "example", type = "item",   currency = 0, cost = 1, weight = 300, maxQuantity = 100, requiredLevel = 1, givenExperience = 10},
  },

}
```

- 3. We go to `tp_trading_port\html\css\style.css` file and we search for `board_button` or a country name as `greece`, there, we will find the ID which is for every created country, this is where you create the correct position for the country flag to be set.
 
Example:

To add turkiye, we create a new line by copying and pasting an existing country, but in our case, we just replace the name of the country to turkiye.

```css
#board_button_turkiye { position: absolute; margin-top: 12vw; margin-left: 39.15vw; height: 1.2vw; width: 1.26vw;}
```

Now, to set the correct position of the flag, you have to play around with `margin-top` and `margin-left` positions by using `vw` after the numbers, **NOT** `px` as the example above.

- 4. It will **NOT** work if you haven't added the country flag where `tp_trading_port\html\img\flags` folder is located.
 
Get an existing country flag image since it has the correct dimensions, replace its name to `turkiye` and add the flag image inside.




