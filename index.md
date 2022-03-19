 # **Meme -Difficulty of Japanese**
## *What I learned after working at a sushi restaurant be like:*
[GitHub](https://github.com/EazerZong/stats220/blob/main/meme.png?raw=true)

![Octocat](https://github.com/EazerZong/stats220/blob/main/meme.png?raw=true)

## My code be like:
```r
library(magick)
normal_mr_incredibles <- image_read("https://static.wikia.nocookie.net/meme/images/a/a7/Uncanny_Phase_1.png/revision/latest?cb=20220215044859") %>%
  image_scale(550)

dark_mr_incredibles <- image_read("https://i.imgflip.com/5unh82.png") %>%
  image_scale(550)

text1 <- image_blank(width = 550, 
                     height = 550, 
                     color = "#FFFFFF") %>%
  image_annotate(text = "Working at a sushi\nrestaurant where\ncustomers say\ngoodbye in Japanese",
                 color = "#000000",
                 size = 50,
                 font = "serif",
                 gravity = "center")

text2 <- image_blank(width = 550, 
                     height = 550, 
                     color = "#FFFFFF") %>%
  image_annotate(text = "When your boss gives\nyou instructions\nin Japanese",
                 color = "#000000",
                 size = 50,
                 font = "serif",
                 gravity = "center")



first_row <- c(normal_mr_incredibles, text1) %>%
  image_append()

second_row <- c(dark_mr_incredibles, text2) %>%
  image_append()

c(first_row, second_row) %>%
  image_append(stack = TRUE)

meme <- image_read("http://localhost:12909/session/preview.png?viewer_pane=1&capabilities=1&host=http%3A%2F%2F127.0.0.1%3A8488")

image_write(meme,path = "meme.png", format="png")
```
