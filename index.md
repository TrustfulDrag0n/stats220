<h1>Assignment 1</h1>

The meme I have created for assignment 1 is about the new game *"Elden Ring"*
that came out last month, **Feb 25** this year. The *"No maidens"* meme has been **trending** for some time now.
the origins of the original meme can be seen here;
[know your meme](https://knowyourmeme.com/memes/no-maidens-maidenless)

<img src="/assets/no_maidens.png" alt="no maiden meme" style="width:300px;"/>

Why I chose this meme;
* The meme is not usually found in the image left. black background, white text right format.
- I thought I'd adapt it into the format that was required.
3. Its been trending
	- I like it

<h3>Here is the code I used to make the meme</h3>

```
library(magick)

melina <- image_read("https://i.imgur.com/EHdQyLC.jpg") %>% 
  image_crop("675x675+225") %>%
  image_scale(500) 
varre <- image_read ("https://i.imgur.com/5PG8gvK.png") %>%
  image_scale(500)

maidenless <- image_blank(width =500, height = 500, color = "#000000") %>%
  image_annotate(text = "No\nMaidens?", 
                 color ="#FFFFFF", 
                 size = 80, 
                 font = "Impact",
                 gravity = "center")

maiden <- image_blank(width =500, height = 500, color = "#000000") %>%
  image_annotate(text = "Maiden\nAcquired", 
                 color ="#FFFFFF", 
                 size = 80, 
                 font = "Impact",
                 gravity = "center")


top_row <- c(varre,maidenless) %>%
  image_append()

bottom_row <- c(melina,maiden) %>%
  image_append()

meme <- c(top_row, bottom_row) %>%
  image_append(stack = TRUE)

image_write(meme, "my_meme.png")
```