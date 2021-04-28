# Accessibility

## Display

### density

**Get current density value**

    adb shell wm density

**Change density value**

    adb shell wm density 352

**Reset density**

    adb shell wm density reset

### font size

    # adb shell settings put system font_scale <scale>
    adb shell settings put system font_scale 10 # 字體放大為10倍
    adb shell settings put system font_scale 1 # 字體設為預設Size

> `1` 為Font size scale的預設值

### magnification

**Change magnification scale**

    adb shell settings put secure accessibility_display_magnification_scale 5.0

**Enable magnification**

    adb shell settings put secure accessibility_display_magnification_enabled 1

**Disable magnification**

    adb shell settings put secure accessibility_display_magnification_enabled 0

> 調整完後Magnification，要啟動才會生效，啟動完後螢幕快速點擊生效即可看到效果。而Disable後則縮放效果。

## Color

### correction

corrections option

| option | code |
| ------ | ---- |
| Monochromatic | 0 |
| Protanomaly | 0 |
| Deuteranomaly | 0 |
| Tritanomaly | 0 |

**Enable display daltonizer**

    adb shell settings put secure accessibility_display_daltonizer_enabled 1

**Disable display daltonizer**

    adb shell settings put secure accessibility_display_daltonizer_enabled 0

**Change color correction mode**

    # Monochromatic
    adb shell settings put secure accessibility_display_daltonizer 0

    # adb shell settings put secure accessibility_display_daltonizer <correction_code>
    
    # Protanomaly
    adb shell settings put secure accessibility_display_daltonizer 11

    # Deuteranomaly
    adb shell settings put secure accessibility_display_daltonizer 12

    # Tritanomaly
    adb shell settings put secure accessibility_display_daltonizer 13

> 與`magnification`相反，需要先行啟用，才能設定顏色校正選項，然後Disable後則一樣消失

### Color inversion

inversion option

| option | code |
| ------ | ---- |
| Enable | 0 |
| Disable | 1 |

    # adb shell settings put secure accessibility_display_inversion_enabled <option_code>
    # Enable the Color inversion
    adb shell settings put secure accessibility_display_inversion_enabled 1

    # Disable the Color inversion
    adb shell settings put secure accessibility_display_inversion_enabled 0

### High contrast text

High contrast text option

| option | code |
| ------ | ---- |
| Enable | 0 |
| Disable | 1 |

    # adb shell settings put secure high_text_contrast_enabled <High_Contrast_Text option_code>

    #Enable High contrast text
    adb shell settings put secure high_text_contrast_enabled 1

    Disable igh contrast text
    adb shell settings put secure high_text_contrast_enabled 1

## Display


## REFERENCE

1. [ADB commands: Accessibility](https://alexzh.com/adb-commands-accessibility/)