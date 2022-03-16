![my_meme](https://user-images.githubusercontent.com/100745235/158490762-c0268e78-ea87-4b57-9075-702e67d1d1fa.png)

# I wanted to do a meme that followed a similar format to memes like the Mr incredible canny meme and the Vince McMahon meme, at first i wanted to use Peter Griffin or Stewie Griffin images but i couldn't find any good ones so i went to Homer and i found much better images.

library(magick)

smiling_homer <- image_read("http://1.bp.blogspot.com/-mOBwKp85SDs/VUOlcE9nVHI/AAAAAAAACJw/nA0FYGcAqJM/s1600/happy_homer.jpg") %>%
  image_scale(400)

happy_homer <- image_read("https://aux.iconspalace.com/uploads/homer-simpson-happy-icon-256.png") %>%
  image_scale(400)

crazy_homer <- image_read("http://crazy-frankenstein.com/pictures-files/the-simpsons-homer-pictures/HomerSimpson42.gif") %>%
  image_scale(400)

image_vector <- c(smiling_homer, happy_homer, crazy_homer)

image_append(image_vector, stack = TRUE)

stats_text <- image_blank(width = 400, 
                          height = 400, 
                          color = "#fff400") %>%
  image_annotate(text = "Going to\nAKL Uni",
                 color = "#000000",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

comp_text <- image_blank(width = 400, 
                         height = 400, 
                         color = "#fff400") %>%
  image_annotate(text = "Majoring\nin Stats",
                 color = "#000000",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

ds_text <- image_blank(width = 400, 
                       height = 400, 
                       color = "#fff400") %>%
  image_annotate(text = "Taking\nStats 220",
                 color = "#000000",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

first_row <- c(smiling_homer, stats_text) %>%
  image_append()

second_row <- c(happy_homer, comp_text) %>%
  image_append()

third_row <- c(crazy_homer, ds_text) %>%
  image_append()

meme <- c(first_row, second_row, third_row) %>%
  image_append(stack = TRUE)
