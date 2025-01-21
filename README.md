# TP TRADING PORT

## Development API Exports

When triggered, it opens the trading port NUI.

```lua
exports.tp_trading_port:OpenTradingNUI() 
```

-- @param data.Level
-- @param data.LevelExperience
-- @param data.HasOrderPickup
-- @param data.IsBusy
-- @param data.CurrentDay
-- @param data.CurrentMonth

```lua
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
