Open Computer Vision
====================

This [MLHub](https://mlhub.ai) package provides a quick introduction
to the functionalities of the Open Computer Vision toolkit.

Currently it only demonstrates the measuring of blurriness of images
through the blurry command.

Visit the github repository for more details:
<https://github.com/gjwgit/opencv>

Usage
-----

- To install mlhub (Ubuntu 18.04 LTS)

```console
$ pip3 install mlhub
```

- To install and configure the demo:

```console
$ ml install gjwgit/opencv
$ ml configure opencv
```

Determine an Image's Blurriness
==============================

The returned measure is probably useful as a measure of
sharpness. The larger the number the sharper the image.

The default threshold for blurriness is 100. Any image with a variance
of the Laplacian less than 100 is regarded as blurry.

Assess the blurriness of a folder of images:
```console
$ for f in *.{png,jpg}; do echo -n "$f "; ml blurry opencv $f; done
street_img1.png Okay 610
street_img2.png Okay 481
street_img3.jpg Blurry 64
street_img4.jpg Okay 903
street_img5.jpg Blurry 91
street_img6.jpg Blurry 71
street_img7.jpg Blurry 75
street_img8.jpg Blurry 60
street_img9.jpg Blurry 93
```

Some specific examples:

![](https://digital-photography-school.com/wp-content/uploads/2014/10/DSC_3913_4_5_6_7_tonemapped-Edit.jpg)
```console
$ ml blurry opencv https:digital-photography-school.com/wp-content/uploads/2014/10/DSC_3913_4_5_6_7_tonemapped-Edit.jpg
Okay 5670
```
![](http://cdn1.thr.com/sites/default/files/2013/11/marina_bay_sands_singapore_a_l.jpg)
```console
$ ml blurry opencv http://cdn1.thr.com/sites/default/files/2013/11/marina_bay_sands_singapore_a_l.jpg
Okay 1303
```
![](https://3.bp.blogspot.com/_Mjt2vy7HUaY/TKY6tQvJzFI/AAAAAAAAAGA/4qwNjH2ivzw/s1600/sharp+focus.jpg)
```console
$ ml blurry opencv https://3.bp.blogspot.com/_Mjt2vy7HUaY/TKY6tQvJzFI/AAAAAAAAAGA/4qwNjH2ivzw/s1600/sharp+focus.jpg
Okay 951
```

![](https://images.pexels.com/photos/338515/pexels-photo-338515.jpeg)
```console
$ ml blurry opencv https://images.pexels.com/photos/338515/pexels-photo-338515.jpeg
Okay 374
```
![](https://www.arrivalguides.com/s3/ag-images-eu/18/20870ca6f7bc086749ea747ec0c8c86d.jpg)
```console
$ ml blurry opencv https://www.arrivalguides.com/s3/ag-images-eu/18/20870ca6f7bc086749ea747ec0c8c86d.jpg
Okay 170
```
![](https://cdn.photographylife.com/wp-content/uploads/2009/09/Red1-960x638.jpg)
```CONSOLE
$ ml blurry opencv https://cdn.photographylife.com/wp-content/uploads/2009/09/Red1-960x638.jpg
Okay 167
```
![](https://www.nyip.edu/images/cms/photo-articles/stop-taking-blurry-pictures.jpg)
```console
$ ml blurry opencv https://www.nyip.edu/images/cms/photo-articles/stop-taking-blurry-pictures.jpg
Blurry 68
```
![](http://getwallpapers.com/wallpaper/full/4/5/4/314199.jpg)
```console
$ ml blurry opencv http://getwallpapers.com/wallpaper/full/4/5/4/314199.jpg
Blurry 43
```
The algorithm is not perfect, or is it just the choice of the
threshold. Perhaps 150 is a better threshold?

![](https://photos1.blogger.com/blogger/4886/2467/1600/23%20-%20Blurry%20Megan%20and%20Colosseum%20at%20night.jpg)
```console
$ ml blurry opencv https://photos1.blogger.com/blogger/4886/2467/1600/23%20-%20Blurry%20Megan%20and%20Colosseum%20at%20night.jpg
Okay 119
```
