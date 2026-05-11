
plot_weight_boxplot_by_sex <- ggplot(bigclass, aes(x = sex, y = weight, fill = sex)) +
  geom_boxplot(width = 0.6) +
  scale_fill_manual(values = c('F' = '#CC79A7', 'M' = '#0072B2')) +
  labs(
    title = 'Weight Distribution by Sex',
    x = 'Sex',
    y = 'Weight'
  ) +
  theme_minimal() +
  theme(
    plot.background = element_rect(fill = 'white'),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    legend.position = 'none'
  )

