
plot_height_weight_scatterplot <- ggplot(bigclass, aes(x = height, y = weight, color = sex)) +
  geom_point(alpha = 0.7, size = 3) +
  scale_color_manual(values = c('F' = '#D55E00', 'M' = '#0072B2')) +
  labs(
    title = 'Height vs. Weight by Sex',
    x = 'Height (inches)',
    y = 'Weight (lbs)'
  ) +
  theme_minimal() +
  theme(
    plot.background = element_rect(fill = 'white'),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    legend.title = element_text(size = 16),
    legend.text = element_text(size = 14)
  )

