# Image Steganography
Steganography is the process of hiding a secret message within a larger one in such a way that someone  cannot know the presence or contents of the hidden message. Although related, Steganography is not to be confused with Encryption, which is the process of making a message unintelligible—Steganography attempts to hide the existence of communication.  
Process

As you know, the images in pixels, of the pixel consists of RGB values. The basic concept, R G B values are to be stored.

We've got two kind of picture, Hide and carrier image. Hide image, we want to embed into the picture carrier. For example, 1.pixel, let's consider the values of R.

Hide image              Carrier image
R = 41                  R = 12
R = 00101001            R = 00001100

Here is the basic logic, the image to hide the RGB values of binary value. Last 2-3 bits (LSB bits), carrier image pixel corresponding to the value of bit (LSB bits) is to bury. The rest of the next pixel value (LSB). Thus, all pixel values of the image that will be hidden when the carrier is embedded into the image, and the process repeats itself.

So why are we in the last 2 or 3 bits of the holes?

Because the last 4 bits into bury, become aware of the change to the human eye. In fact, the last 3 bits could even be risky. 2-bit exact result. I buried the last 2 bits in this program. Let's continue from the example above.

Hide image              Carrier image
R = 00101001            R = 00001100 (1.Pixel)
                        G = 00010111
                        B = 01001001
                        R = 01011011 (2.Pixel)
                        G = 10100111
                        B = 11100101

After running the program, into the carrier image, the picture to hide 1. Pixel (R value) notice was buried..

Hide image              Carrier image
                            old         new
R = 00101001            R = 00001100 -> 00001100 (1.Pixel)
                        G = 00010111 -> 00010110
                        B = 01001001 -> 01001010
                        R = 01011011 -> 01011001 (2.Pixel)
                        G = 10100111 -> 10100111
                        B = 11100101 -> 11100101

    Steganography and Secret Sharing is used with the, reverse engineering will be quite difficult.

Dimension

The hidden image size 25 x 30, To completely cover up the image of this size, carrier size is calculated as follows.

0 <= 25 x 30 <= (M X N X S)/8   

    M X N The size of the image carrier
    S how many bits to embed (Last bits !)

Run

    Required Package for Linux

$ sudo apt-get install monodevelop

$ msc Program.cs
$ mono Program.exe