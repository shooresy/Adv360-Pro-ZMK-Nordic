# Kinesis Advantage360 Pro - Nordic Layout

ZMK firmware configuration for Kinesis Advantage360 Pro with Nordic character support (å, ä, ö).

## What's Different

This is a fork of the official [KinesisCorporation/Adv360-Pro-ZMK](https://github.com/KinesisCorporation/Adv360-Pro-ZMK) repository with Nordic character support added.

### Nordic Character Layout

The keymap has been modified to include Nordic characters in strategic positions:

| Key Position | Tap | Shift + Key | Nordic Layout Result |
|-------------|-----|-------------|---------------------|
| **P key position (top right)** | `[` | `\` | `å` when using Nordic OS layout |
| **Semicolon position** | `;` | `:` | `ö` when using Nordic OS layout |
| **Quote position** | `'` | `"` | `ä` when using Nordic OS layout |

### How It Works

Instead of using Unicode characters (which can cause compatibility issues), this keymap sends standard keycodes that are interpreted as Nordic characters when you have a Nordic keyboard layout active in your operating system.

**Key Mapping Strategy:**
- Uses `[` (left bracket) keycode which maps to `å` in Nordic layouts
- Uses `;` (semicolon) keycode which maps to `ö` in Nordic layouts  
- Uses `'` (apostrophe) keycode which maps to `ä` in Nordic layouts
- Shift combinations provide traditional symbols (`\`, `:`, `"`)

## OS Setup Required

⚠️ **Important:** You must set your OS keyboard layout to a Nordic layout for the special characters to work.

### Windows 11
1. Go to Settings → Time & Language → Language & Region
2. Add Swedish, Norwegian, Danish, or Finnish language
3. Set the keyboard layout to the Nordic language you added
4. Use `Win + Space` to switch between layouts

### Linux
```bash
setxkbmap se  # For Swedish
setxkbmap no  # For Norwegian  
setxkbmap dk  # For Danish
setxkbmap fi  # For Finnish
```

### macOS
1. System Preferences → Keyboard → Input Sources
2. Add Swedish, Norwegian, Danish, or Finnish
3. Use Control+Space to switch between layouts

## Building the Firmware

### Using GitHub Actions (Recommended)

1. **Fork this repository**
2. **Enable GitHub Actions** on your fork
3. **Push a commit** to trigger the build
4. **Download the firmware** from the Actions tab under "Artifacts"

### Local Building

Follow the original [Kinesis build instructions](https://github.com/KinesisCorporation/Adv360-Pro-ZMK#building-the-firmware-in-a-local-container) but use this repository instead.

## Flashing

Follow the standard [Kinesis flashing instructions](https://github.com/KinesisCorporation/Adv360-Pro-ZMK#flashing-firmware):

1. Put left half into bootloader mode (Mod+macro1)
2. Copy `left.uf2` to the USB drive
3. Put right half into bootloader mode (Mod+macro3)  
4. Copy `right.uf2` to the USB drive
5. Enjoy Nordic typing!

## Testing Nordic Characters

After flashing and setting up your Nordic OS layout:

1. **Test å**: Tap the key where `P` used to be (top right of left hand)
2. **Test ö**: Tap the semicolon key (right hand, home row)
3. **Test ä**: Tap the quote key (right hand, next to semicolon)

## Troubleshooting

### Nordic characters not appearing
- ✅ Ensure you have a Nordic keyboard layout active in your OS
- ✅ Check that both halves of the keyboard were flashed successfully
- ✅ Try switching keyboard layouts with `Win+Space` (Windows) or equivalent

### Wrong characters appearing
- The keymap sends standard keycodes that only become Nordic characters with a Nordic OS layout
- Switch to Swedish, Norwegian, Danish, or Finnish keyboard layout in your OS

## Credits

- Based on the official [Kinesis Advantage360 Pro ZMK Config](https://github.com/KinesisCorporation/Adv360-Pro-ZMK)
- Nordic character implementation focuses on compatibility and simplicity
- Uses proven mod-morph behaviors for traditional symbol access

Enjoy your Nordic typing experience! 🇸🇪🇳🇴🇩🇰🇫🇮
