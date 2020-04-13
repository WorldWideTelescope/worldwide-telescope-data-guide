+++
title = "Processing Panoramas"
weight = 600
sort_by = "weight"
insert_anchor_links = "right"
+++

Panoramas are wide field of view images taken with either wide-angle fish-eye
lenses or stitched together from individual images take of a wide field of
view scene.

This tutorial will walk through how to process these data so that they can be
TOAST projected into a multi-resolution format that can be hosted in the
Cloud.


# If you have a collection of images

Many high resolution panoramas, especially ones obtained by remote space
craft, are taken as a collection of individual images.  In the case where you
have a collection the first step is to stitch them together to create a single
panorama image that can be processed for WWT (see below).

There are several programs that

1. PTAssembler —
   [http://www.tawbaware.com/ptasmblr.htm](http://www.tawbaware.com/ptasmblr.htm)
2. Auto Stitch —
   [http://matthewalunbrown.com/autostitch/autostitch.html](http://matthewalunbrown.com/autostitch/autostitch.html)
3. GigaPan (hardware mount + software) —
   [http://www.gigapan.com/](http://www.gigapan.com/)
4. Image Composite Editor —
   [http://research.microsoft.com/en-us/um/redmond/projects/ice/](http://research.microsoft.com/en-us/um/redmond/projects/ice/)

This tutorial uses Image Composite Editor (ICE).

Collect the images that cover as much of your field of view as possible. They
do not need to be in any specific order or have any naming convention.

1. Startup ICE.
2. Click "New Panorama From Images".
3. Navigate to the folder with the images. Assuming the folder had only the
   images to be stitched together, click Control-A to select all the images
   and then click "Open".
4. Under "Camera Motion" in the upper right, make sure "Auto-detect" is
   clicked.
5. At the upper menu, click "Stitch".
6. When it is finished it will show the images stitched together and
   projected. Leave the projection as "Cylindrical".
7. In the upper menu, click "Crop". You should probably not apply any crops.
8. In the upper menu, click "Export". In the upper right don't change any of
   the parameters, and click "Export to disk…"


# If you have a panoramic image already

{{ youtube(id=NNBVB2QlADE) }}

Many cameras can obtain panoramic images directly. Examples are Ricoh Theta
([https://theta360.com/en/](https://theta360.com/en/)) and Kodak Pixpro
([http://kodakpixpro.com/Americas/cameras/actioncamera/sp360.php](http://kodakpixpro.com/Americas/cameras/actioncamera/sp360.php))
cameras. Even smart phones can capture panoramic images with software such as
Microsoft's [Photosynth](https://en.wikipedia.org/wiki/Photosynth). This could
be useful in capturing panoramic views of observatories or observational
locations. Of course another important type of data are panoramic views of
surfaces of other bodies of the Solar System. However the panoramic image was
obtained, this image is the input to the next step, which is to use the
SphereToaster tool.

1. Open the panorama and make sure that it is of the correct size. The input
   panorama file should be in equi-rectangular (aka cylindrical equidistant)
   projection. In this projection the panorama should be twice as wide as it
   is tall and should cover the entire 360 field of view. If the image is
   projected correctly but isn't the entire size, I recommend that you pad the
   image with black space. In this example, we will use a free Windows program
   called Irfanview ([http://www.irfanview.com/](http://www.irfanview.com/)).
   You can open the image and the image dimensions are shown in the lower left
   corner. In this example, the image is 7872×1752 pixels.
   ![](irfanview-sample.jpg)
2. If you need to pad the image to be 2:1 then in Irfanview, under the Image
   menu, select "Change canvas size". In this example, the width of the image
   is 360 degrees but it covers the middle part and does not go to the top and
   bottom. Given that the width is 7872 the final height should be half that
   or 3936 pixels. Since the image is actually 1752 pixels high we have to pad
   3936 - 1752 = 2184 pixels. This padding needs to be split equally to be added
   to the top and bottom; that is, 1092 to top and bottom and 0 to left and
   right.
   ![](canvas-size.jpg)
3. Then save the image. It should now have the dimensions 7872×2936.
4. Download the WWT SDK, available here: On the Tools page:
   [http://www.worldwidetelescope.org/Download/Tools](http://www.worldwidetelescope.org/Download/Tools)
   click on "SDK with data pipeline and original ADK tools" which should link
   to:
   [http://wwtweb.blob.core.windows.net/drops/WWTSDK.msi](http://wwtweb.blob.core.windows.net/drops/WWTSDK.msi).
5. Install the SDK. It will install a folder:
   `C:\Program Files (x86)\Microsoft Research\WorldWide Telescope SDK`.
   Go into that folder and then into "Sphere
   Toaster" and then execute the program: `SphereToaster.exe`.
6. In SphereToaster start with the "Input" tab. Click "Open" and navigate to
   the padded image in equi-rectangular projection. Assuming you did your padding
   correctly, you should not have to change anything.
   ![](sphere-toaster-preview.jpg)
7. Under the Output tab, select a folder where the processed files will be
   created. Note, that the total size of the processed data can be much more
   than the original, especially if the input image is compressed with much
   black, so make sure the output drive has sufficient space. The default
   Project Name is taken from the input file name, which you can change. This
   is the name of the output WTML file.
8. Under Type, choose "Panorama". In order to preserve transparency, keep the
   output format as PNG and do not select JPEG.
9. Since you have padded the image in the previous step, under "Fill Option"
   select "No fill".
   ![](sphere-toaster-no-fill.jpg)
10. Under the WTML tab, you can give the descriptive information for the
    image. Under Title, you should give a descriptive (and short) title that
    will show up in WWT. Under Credits, you can put the caption information,
    including the credit to the person or organization who owns the copyright
    of the image. You can specify the URL (Credits URL) which points to web
    page that described the image or data. Assuming you are going to make this
    panorama available on-line you can specify the URL to the web server that
    will serve the panorama data (Storage URL). Note this can be changed
    easily if you don’t set this now or change the location of the server
    later.
    ![](sphere-toaster-metadata.jpg)
11. When you are finished entering this metadata, go back to the Output tab
    and click on: `Generate Pyramid + WTML`. This will take a while. For this
    example (7872×3936) it took about 40 minutes on a reasonably fast PC.
    Note, that while it is working the GUI doesn't get updated and the window
    banner will show "WWT SphereToaster (Alpha) (Not Responding." It is
    actually running so don’t close the window. It will report some progress
    in the Messages window in the lower right of the Output tab. When you
    first load the image it will report that it found the input image (“Loaded
    C:\Users\docto\Downloads\Chang’e 3.jpg” in this example). You can check on
    it with the task manager or by looking at the properties of the output
    folder; the total output size should be increasing as the process runs and
    generates more files. When it is finished SphereToaster will report the
    number of tiles created and time to process the data.
12. When this is complete, the process will create the following:
    - Folder full of tiles, e.g., `Chang’e 3`
    - WTML file to use locally, `Chang’e 3LOCAL.wtml`. This is only used for
      local testing and cannot be shared outside the machine you are working
      on.
    - WTML file to use when the data are on a web server, `Chang’e 3.wtml`.
      Once the data are processed and moved to the specified server, sharing
      this file will provide access to it.
    - Thumbnail; the name is a lower case version of the title with spaces
      replaced with underscores (e.g., `chang’e_3.jpg`)
13. You can view the generated panorama by starting WorldWide Telescope and
    then double-clicking on the local version of the WTML file. In this
    example it is `Chang'e 3LOCAL.wtml`. Note, that this points to the
    specific location on disk where you specified the output, so if you move
    that folder you have to edit this local WTML file.
14. The other version of the WTML file (`Chang'e 3.wtml`) is setup to point to
    a data on a web server. In the WTML file, you should review the location
    (`Url="[Storage URL]/Chang'e 3 Pano/{1}/{3}/{3}_{2}.jpg`", where “Storage
    URL” was specified in the WTML tab). After the image pyramid is created,
    you can move it to the web server and then use the `Chang’e 3.wtml` to
    access the data over the web. If you move the data to a different web
    server, you need to change the server address in the Url tag in the WTML
    file.

You can find additional information on how to use SphereToaster tool in the
SDK (as well as the other tools) in the
[Sphere Toaster section](@/windows-data-tools/sphere-toaster/index.md).
