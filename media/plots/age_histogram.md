
plot_age_histogram <- ggplot(bigclass, aes(x = age)) +
  geom_histogram(binwidth = 1, fill = '#0072B2', color = 'white') +
  labs(
    title = 'Distribution of Age',
    x = 'Age',
    y = 'Frequency'
  ) +
  theme_minimal() +
  theme(
    plot.background = element_rect(fill = 'white'),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14)
  )

