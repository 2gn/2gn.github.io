#linux #ibus #skk

参考: https://akaneko85r.hatenablog.com/entry/2015/02/15/174847


```shell

sudo vi /usr/share/ibus/component/skk.xml

```

```git us.patch

diff --git a/skk.xml b/skk-a.xml
index b7056d3..cee0539 100644
--- a/skk.xml
+++ b/skk-a.xml
@@ -17,7 +17,7 @@
                        <license>GPL</license>
                        <author>Daiki Ueno &lt;ueno@unixuser.org&gt;</author>
                        <icon>/usr/share/ibus-skk/icons/ibus-skk.svg</icon>
-                       <layout>us</layout>
+                       <layout>ja</layout>
                        <longname>SKK</longname>
                        <description>SKK Input Method</description>
                        <rank>70</rank>
```
