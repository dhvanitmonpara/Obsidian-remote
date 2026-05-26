**Images:** 
You can add images using `<image>` tag.
```html
<image src="input/source/here" alt="input/alternative/text/here" height="size" width="size">
```
Note that you can also change image size from image link.

**Audio:** 
You can add audio files using `<audio>` tag.
```html
<audio src="input/source/here" controls="Go to MDN for details">
```
Use javascript and CSS for styling your audio/music bar.

**Video:** 
You can add videos using `<video>` or `<iframe>` tag.

`<video>` tag:
```html
<video src="input/source/here" controls="Go to MDN for details" height="size" width="size">
```

`<iframe>` tag:

```html
<iframe src="input/source/here" frame-border="size for eg. 1px" height="size" width="size" autoplay=1 mute=0>
```
`1` and `0` means true and false in `autoplay`and `mute` attributes and it is not defined in double quotation marks.

Let's see how to embade a youtube video:

```html
<iframe src="https://www.youtube.com/watch?/afenbs">

<!--Replace "watch?" With "embade"-->

<iframe src="https://www.youtube.com/embade/afenbs">
```
It converts your video in embade form.

**Bookmarks:** 
Whenever you want to give a bookmark to any perticular tag, just give it `id` and create `<a>` tag to link it.

```html
<!--Give bookmark to section tag-->

<section Id="class-videos"></section>

<a href="#class-videos">class videos</a>

<!--It will work like a page bookmark, whenever you click on class videos(which is anchor tag), you will redirect to the section tag-->
```

==MDN wala statement==.