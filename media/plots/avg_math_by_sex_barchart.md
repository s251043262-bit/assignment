
plot_avg_math_by_sex <- bigclass %>%
  group_by(sex) %>%
  summarise(avg_math = mean(Math)) %>%
  ggplot(aes(x = sex, y = avg_math, fill = sex)) +
  geom_bar(stat = 'identity', width = 0.7) +
  scale_fill_manual(values = c('F' = '#D55E00', 'M' = '#009E73')) +
  labs(
    title = 'Average Math Score by Sex',
    x = 'Sex',
    y = 'Average Math Score'
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

