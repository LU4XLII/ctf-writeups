# Don't blink - 100
`Do you have persistence of vision? Well try it out with this file.`

The file:

![persistant.gif](/../master/evlzctf/persistant.gif)

I extracted the frames from the gif and bended they together, using Pillow.

```python
from PIL import Image

im = Image.open('persistant.gif')

for i in range(im.n_frames):
    im.seek(i)
    im.save('./gif/'+str(i)+'.png')

img = Image.open("./gif/0.png").convert("RGBA")

for i in range(1, im.n_frames):
    img2 = Image.open('./gif/'+str(i)+'.png').convert("RGBA")
    img = Image.blend(img, img2, alpha=0.1)

img.save('result.png')
```

Result:

![persistant.gif](/../master/evlzctf/result.png)

Flag: `evlz{catch_me}ctf`
