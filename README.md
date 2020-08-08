# 080820_GGScatterPlot
GG Scatter Plot of in-class activity + Individual lightning talk
#data visualize for individual lighting talk presentation
ggplot(data = penguins, aes(x = species, y = island)) +
  #geom_point changes the characteristic of the points in scatter plot
  #aes uses the species and island to define what the output of color and shape will be
  geom_point(aes(color = island, 
                 shape = species),
             #change the size of point, alpha is opacity, and position jitter prevents overlap
             size = 3,
             alpha = 0.65, 
             position = "jitter") +
  #theme_minimal() +
  #the hashtag numbers are hexcodes for colors, na.translate = F is a clever way of removing the NA count
  scale_color_manual(values = c("#FFD750","#E29CC3", "#1BDAC0"), 
                     na.translate = F) +
  #lab(...) changes the labels of the graph
  labs(title = "Distribution of Penguin Species across Islands",
       #renaming the x-axis, y-axis, and the legend titles of color and shape to what is in quotations
       x = "Species",
       y = "Island",
       color = "Penguin island",
       shape = "Penguin species") +
  theme_minimal()
