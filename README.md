# Instax Print

Print to an instax mini LiPlay (and the mini/SQUARE/WIDE Link printers) over Web Bluetooth, from a computer or an iPhone, without Fujifilm's app.

**Open it:** https://splch.github.io/instax-print/

## Browsers

- **Computer / Android:** Chrome or Edge.
- **iPhone / iPad:** iOS browsers have no Web Bluetooth. Install the free [Bluefy – Web BLE Browser](https://apps.apple.com/app/bluefy-web-ble-browser/id1492822055) app and open the link above in it.

## Printing

1. Turn the camera on and close the official instax app.
2. Tap **Connect** and choose the `INSTAX-…(IOS)` entry. That is the BLE endpoint (FA:AB:BC:…). The `(ANDROID)` endpoint (88:B4:36:…) is Classic Bluetooth, which browsers can't use.
3. Put the camera on the shooting screen, not a menu.
4. Pick a photo, frame it, and print. **Test transfer only** sends the photo without printing, so it uses no film.

## If it won't connect

The camera remembers one device. When switching devices, or after a failed session, start fresh on both sides:

1. Delete the registration in the camera's Bluetooth menu.
2. Forget the INSTAX device in the computer's or phone's Bluetooth settings.
3. Turn the camera off and on, then connect again.

## Run locally

    python3 -m http.server 8765 --bind 127.0.0.1

Then open http://localhost:8765 in Chrome.

Protocol is based on [javl/InstaxBLE](https://github.com/javl/InstaxBLE) (see its issues #2 and #18 for LiPlay chunk sizes and size limits).
