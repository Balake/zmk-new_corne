# Eyelash Corne ZMK Repository

**This keyboard is not the same as [foostan's Corne](https://github.com/foostan/crkbd). It will not work with standard `corne` firmware.**

![Photo of Eyelash Peripherals Corne](https://ae01.alicdn.com/kf/Sa797fee25edd44248fbfdb0e13d44e00B.jpg)

## Instructions

1. [Fork this repository](https://docs.github.com/en/get-started/quickstart/fork-a-repo#forking-a-repository).
2. [Click the **Actions** tab and make sure the workflow is enabled](https://docs.github.com/en/actions/managing-workflow-runs-and-deployments/managing-workflow-runs/disabling-and-enabling-a-workflow#enabling-a-workflow).
3. Make sure the `eyelash_corne` project in [`config/west.yml`](config/west.yml) still works. The `boards/arm/eyelash_corne` folder will be downloaded from this URL.
4. If there is still a `boards/arm/eyelash_corne` folder in your fork, delete it.

### How to change keymap
1. Steps 1-2 above (or fork this repo)
2. Change keymap and push changes. I recommend using [keymap editor](https://nickcoutsos.github.io/keymap-editor/).
3. Download artifacts.
4. Plug in either board, double press sys_reset button or &bootloader
5. Drag the appropriate half of .uf2 file to NICE NANO usb device that should show up. Note: on macOS, this can crash finder lol but it still works

**If you already have a ZMK config repository, [you can add this one as a module instead of forking](https://zmk.dev/docs/features/modules#building-with-modules).**

## Keymap Diagram

![Diagram of config/eyelash_corne.keymap](keymap-drawer/eyelash_corne.svg "generated by @caksoylar's Keymap Drawer")

## Mouse Support

:warning: This repository defaults to an EXPERIMENTAL mouse movement branch which is slated for eventual merge into ZMK, but is not guaranteed to be stable. For more information, see [beta testing](https://zmk.dev/docs/features/modules#beta-testing) and [PR #2477](https://github.com/zmkfirmware/zmk/pull/2477).

If desired, edit your `config/west.yml` to switch back to `zmkfirmware`'s `main` branch:

```diff
diff --git a/config/west.yml b/config/west.yml
index ac30a68..70ad540 100644
--- a/config/west.yml
+++ b/config/west.yml
@@ -13,8 +13,8 @@ manifest:
       url: https://github.com/a741725193/zmk-new_corne
       revision: main
     - name: zmk
-      remote: petejohanson
-      revision: feat/pointers-with-input-processors
+      remote: zmkfirmware
+      revision: main
       import: app/west.yml
   self:
     path: config
```
