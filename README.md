# ggplot2 tech themes, scales, and geoms




### Install ggtech:


```r
devtools::install_github("ricardo-bion/ggtech", 
                          dependencies=TRUE)
```

### Use ggtech:

Make sure to install the required fonts (instructions at the end of this file).


```r
library(ggtech)

d <- qplot(carat, data = diamonds[diamonds$color %in%LETTERS[4:7], ], geom = "histogram", bins=30, fill = color)
```


Tech themes and scales:


```r
d + theme_tech(theme="airbnb") + 
  scale_fill_tech(theme="airbnb") + 
  labs(title="Airbnb theme", 
       subtitle="now with subtitles for ggplot2 >= 2.1.0")
```

![](README_files/figure-html/unnamed-chunk-3-1.png)


```r
d + theme_airbnb_fancy() + 
  scale_fill_tech(theme="airbnb")  + 
  labs(title="Airbnb theme", 
       subtitle="now with subtitles for ggplot2 >= 2.1.0")
```

![](README_files/figure-html/unnamed-chunk-4-1.png)




```r
d + theme_tech(theme="etsy") + 
  scale_fill_tech(theme="etsy") + 
  labs(title="Etsy theme", 
       subtitle="now with subtitles for ggplot2 >= 2.1.0")
```

![](README_files/figure-html/unnamed-chunk-5-1.png)




```r
d + theme_tech(theme="facebook") +
  scale_fill_tech(theme="facebook") + 
  labs(title="Facebook theme", 
       subtitle="now with subtitles for ggplot2 >= 2.1.0")
```

![](README_files/figure-html/unnamed-chunk-6-1.png)



```r
d + theme_tech(theme="google") + 
  scale_fill_tech(theme="google") + 
  labs(title="Google theme", 
       subtitle="now with subtitles for ggplot2 >= 2.1.0")
```

![](README_files/figure-html/unnamed-chunk-7-1.png)



```r
d + theme_tech(theme="twitter") + 
  scale_fill_tech(theme="twitter") + 
  labs(title="Twitter theme", 
       subtitle="now with subtitles for ggplot2 >= 2.1.0")
```

![](README_files/figure-html/unnamed-chunk-8-1.png)



Tech geoms, inspired by [emoGG](https://github.com/dill/emoGG).



```r
d2 <- data.frame(x = c(1:4, 3:1), y=1:7)
```



```r
ggplot(aes(x,y), data=d2) + 
  geom_tech(size=0.25, theme="airbnb") + 
  theme_tech("airbnb") +
  ggtitle("Airbnb geom")
```

![](README_files/figure-html/unnamed-chunk-10-1.png)



```r
ggplot(aes(x,y), data=d2) + 
  geom_tech(size=0.15, theme="etsy") + 
  theme_tech("etsy")+
  ggtitle("Etsy geom")
```

![](README_files/figure-html/unnamed-chunk-11-1.png)


```r
ggplot(aes(x,y), data=d2) + 
  geom_tech(size=0.15, theme="facebook") + 
  theme_tech("facebook")+
  ggtitle("Facebook geom")
```

![](README_files/figure-html/unnamed-chunk-12-1.png)



```r
ggplot(aes(x,y), data=d2) + 
  geom_tech(size=0.25, theme="google") + 
  theme_tech("google" ) +
  ggtitle("Google geom")
```

![](README_files/figure-html/unnamed-chunk-13-1.png)



```r
ggplot(aes(x,y), data=d2) + 
  geom_tech(size=0.15, theme="twitter") + 
  theme_tech("twitter") +
  ggtitle("Twitter geom")
```

![](README_files/figure-html/unnamed-chunk-14-1.png)



### Install fonts:

You have to install the necessary fonts manually before using `ggtech`. Mofidy the `destfile` if you are using Windows or Unix.



```r
library(extrafont)

## Facebook 
download.file("http://social-fonts.com/assets/fonts/facebook-letter-faces/facebook-letter-faces.ttf", "/Library/Fonts/facebook-letter-faces.ttf", method="curl")

font_import(pattern = 'facebook-letter-faces.ttf', prompt=FALSE)


## Google 
download.file("http://social-fonts.com/assets/fonts/product-sans/product-sans.ttf", "/Library/Fonts/product-sans.ttf", method="curl")

font_import(pattern = 'product-sans.ttf', prompt=FALSE)


## Airbnb 
download.file("https://dl.dropboxusercontent.com/u/2364714/airbnb_ttf_fonts/Circular%20Air-Medium%203.46.45%20PM.ttf", "/Library/Fonts/Circular Air-Medium 3.46.45 PM.ttf", method="curl")

download.file("https://dl.dropboxusercontent.com/u/2364714/airbnb_ttf_fonts/Circular%20Air-Bold%203.46.45%20PM.ttf", "/Library/Fonts/Circular Air-Bold 3.46.45 PM.ttf", method="curl")

download.file("https://www.dropbox.com/sh/2156fxhf5t43nbe/AAC062NgDCaAPZ1RNhrc9l51a/circularstd-bold.ttf?dl=0",
"/Library/Fonts/Circular Ando-Bold.tff", method="curl")

download.file("https://www.dropbox.com/sh/2156fxhf5t43nbe/AAAoJkV5DB3C5-rwpq7SFhDUa/CircularStd-Book.ttf?dl=0",
"/Library/Fonts/Circular Ando-Book.tff", method="curl")

download.file("https://www.dropbox.com/sh/2156fxhf5t43nbe/AAC64tg4sijObd-nqjoE4yrsa/circularstd-medium.ttf?dl=0",
"/Library/Fonts/Circular Ando-Medium.tff", method="curl")

font_import(pattern = 'Circular', prompt=FALSE)


## Etsy 
download.file("https://www.etsy.com/assets/type/Guardian-EgypTT-Text-Regular.ttf", "/Library/Fonts/Guardian-EgypTT-Text-Regular.ttf", method="curl")

font_import(pattern = 'Guardian-EgypTT-Text-Regular.ttf', prompt=FALSE)


## Twitter 
download.file("http://social-fonts.com/assets/fonts/pico-black/pico-black.ttf", "/Library/Fonts/pico-black.ttf", method="curl")

download.file("http://social-fonts.com/assets/fonts/arista-light/arista-light.ttf", "/Library/Fonts/arista-light.ttf", method="curl")

font_import(pattern = 'pico-black.ttf', prompt=FALSE)
font_import(pattern = 'arista-light.ttf', prompt=FALSE)

## Ando
download.file("https://www.dropbox.com/sh/yofdf3ymm8zgsef/AABhDQUCVFr05fbYyWluCLPha/ReplicaMono.otf?dl=0",
"/Library/Fonts/ReplicaMono.otf", method="curl")

font_import(pattern = "ReplicaMono.otf", prompt=FALSE)
```
