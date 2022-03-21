# stats220
https://github.com/TrustfulDrag0n/stats220

This repository is for my Stats 220 Semester 1 2022 Course
I will be using it to submit assignments throughout the course.

**#Assignment 1#**

The meme I have created for assignment 1 is about the new game *"Elden Ring"*
that came out **Feb 25** last month. The *"No maidens"* meme has been **trending** for some time now
and I thought i'd adapt it into the format that was required.
the origins of the original meme can be seen here;
[know your meme](https://knowyourmeme.com/memes/no-maidens-maidenless)
[![no maiden meme](/assets/no_maidens.png "no maiden meme")](https://imgur.com/SSMytT2)
The meme is not usually found in the image left. black background, white text right format.

**###Here is the code I used to make the meme###**
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