# Waybar integration

Add the module to your Waybar configuration and include it in the desired
module list:

```jsonc
{
  "modules-right": [
    "custom/niri-column-indicator"
  ],
  "custom/niri-column-indicator": {
    "exec": "niri-column-indicator --inactive ○ --active ● --hide-single",
    "return-type": "json"
  }
}
```

Ensure `niri-column-indicator` is on Waybar's `PATH`.

Style the module in your Waybar stylesheet with the
`#custom-niri-column-indicator` selector.
