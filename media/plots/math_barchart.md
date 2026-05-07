
library(ggplot2)
library(plotly)
library(dplyr)

min_math <- min(bigclass$Math, na.rm = TRUE)
max_math <- max(bigclass$Math, na.rm = TRUE)
bin_width <- 50
breaks <- seq(floor(min_math / bin_width) * bin_width, ceiling(max_math / bin_width) * bin_width + bin_width, by = bin_width)

bigclass_binned <- bigclass %>% 
  mutate(Math_Bin = cut(Math, breaks = breaks, include.lowest = TRUE, right = FALSE)) %>% 
  group_by(Math_Bin) %>% 
  summarise(Count = n()) %>% 
  ungroup()

p_bar <- ggplot(bigclass_binned, aes(x = Math_Bin, y = Count, fill = Math_Bin)) + 
  geom_bar(stat = "identity", color = "white", show.legend = FALSE) + 
  scale_fill_manual(values = rep(c("#0072B2", "#D55E00", "#009E73", "#CC79A7"), length.out = nrow(bigclass_binned))) + 
  labs(
    title = "Bar Chart of Math Scores (Binned)",
    x = "Math Score Bins",
    y = "Frequency"
  ) + 
  theme_minimal() + 
  theme(
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14, angle = 45, hjust = 1),
    axis.text.y = element_text(size = 14),
    panel.background = element_rect(fill = "white", colour = NA),
    plot.background = element_rect(fill = "white", colour = NA)
  )

p_bar_plotly <- ggplotly(p_bar)

htmlwidgets::saveWidget(p_bar_plotly, "media/plots/math_barchart.html", selfcontained = TRUE)

