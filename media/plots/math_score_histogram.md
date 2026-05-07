```R
library(ggplot2)
library(plotly)
library(htmlwidgets)

p <- ggplot(bigclass, aes(x = Math)) +
  geom_histogram(binwidth = 50, fill = '#0072B2', color = 'black', alpha = 0.7) +
  labs(title = 'Distribution of Math Scores', x = 'Math Score', y = 'Frequency') +
  theme_minimal() +
  theme(
    plot.background = element_rect(fill = 'white', color = NA),
    panel.background = element_rect(fill = 'white', color = NA),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14)
  )

pp <- ggplotly(p)

htmlwidgets::saveWidget(pp, file = "/content/project/media/plots/math_score_histogram.html", selfcontained = TRUE)
```

