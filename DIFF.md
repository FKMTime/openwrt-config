# DIFF (FOR NOW,  LATER I WILL JUST PASTE PATCH FILE)

```
diff --git a/target/linux/bcm27xx/image/cmdline.txt b/target/linux/bcm27xx/image/cmdline.txt
index bdd1e59a09..fd3e668f19 100644
--- a/target/linux/bcm27xx/image/cmdline.txt
+++ b/target/linux/bcm27xx/image/cmdline.txt
@@ -1 +1 @@
-console=tty1 console=serial0,115200 root=@ROOT@ rootfstype=squashfs,ext4 rootwait
+console=tty1 root=@ROOT@ rootfstype=squashfs,ext4 rootwait
diff --git a/target/linux/bcm27xx/image/config.txt b/target/linux/bcm27xx/image/config.txt
index db35d72ab7..4ea3c66179 100644
--- a/target/linux/bcm27xx/image/config.txt
+++ b/target/linux/bcm27xx/image/config.txt
@@ -12,3 +12,4 @@ include distroconfig.txt

 [all]
 # Place your custom settings here.
+dtparam=krnbt=on
diff --git a/target/linux/bcm27xx/image/distroconfig.txt b/target/linux/bcm27xx/image/distroconfig.txt
index b09e5b8466..2745a1e211 100644
--- a/target/linux/bcm27xx/image/distroconfig.txt
+++ b/target/linux/bcm27xx/image/distroconfig.txt
@@ -7,10 +7,10 @@
 #  which changes the core frequency to a fixed value and impacts performance.
 # See https://www.raspberrypi.com/documentation/computers/configuration.html#mini-uart-and-cpu-core-frequency
 [pi0w]
-dtoverlay=disable-bt
+#dtoverlay=disable-bt
 [pi3]
-dtoverlay=disable-bt
+#dtoverlay=disable-bt
 [pi4]
-dtoverlay=disable-bt
+#dtoverlay=disable-bt
 # Run as fast as firmware / board allows
 arm_boost=1
(END)
```
