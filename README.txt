Fun story.  Not everything that reads jpegs obeys the Orientation EXIF data when it's displaying jpegs.  Web browsers
generally don't.  They probably never will since the precedent is so thoroughly set by now.  Some cameras get faster
image recording by using the orientation sensor to merely write the EXIF:Orientation flag rather than changing
the raster data itself.

Of course, plenty of desktop image browsing programs will obey this and display your pictures oriented naturally for
you.  However, it's nice to not have files end up sideways when you upload them.  At this moment this program is broken
as it doesn't properly clear the EXIF:Orientation flag (set it to numeric value 1) as some experimentation into using
PythonMagick instead of executing subprocesses to do image mangling was under way.  However, it turns out PythonMagick
has got some deficiencies on this front: http://www.imagemagick.org/discourse-server/viewtopic.php?f=1&t=15841

I've since learned that this charming little command does... the entire job of exifrotate:

    jhead -autorot *.jpg

So, this project is moot.
