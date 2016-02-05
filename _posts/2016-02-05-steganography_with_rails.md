---
layout: post
title: Steganography with ruby
---

So recently I decided to look into what are some fun science-y things one can do with ruby, despite being a less popular language with researchers in comparison to python. So I decided to look into what one can do to embed some information into a png image.  

Here after some digging around I decided the RMagick library has the basic components we need to play around with pixels. (I did try to manipulate the raw binary file with much lack of success, thank god we have libraries)  

The idea goes like this: given an image and a string of message one wants to embed, we try to replace the least significant bits of each of the RGB colors with bits of the information we want to embed. Every byte is 8 bits, so we can divide the bits into 3-2-3 -> RGB. A bit of bit manipulation goes on here, intro CS class to the rescue.  

To give an example, we want to loop through the original image's pixels, embed the right bits into the right colors, then store it in a new pixel struct(what is it in ruby?) that will become the new pixel at the exact same coordinates for the output image:  


{% highlight ruby %}
    new_red = (pixel.red & 0xFFF8) | ((message[index].unpack("C*")[0] >> 5) & 0x07)
{% endhighlight %}
And we do that for as long as it takes to finish embedding the secret message, then for the rest of the pixels we just copy it over: 
{% highlight ruby %}
  out.pixel_color(x,y, pixel)
end
{% endhighlight %}

Fairly straight-forward, was not at all intuitive to me until I write the numbers on paper. To add this processing to an image in rails, if your image handler is carrierwave for instance, you could define a custom method and process it accordingly. 