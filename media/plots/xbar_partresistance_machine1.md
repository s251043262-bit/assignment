
filtered_data <- subset(X010, Machine == 1 & Temperature == 303 & Pressure == 100)
qcc_obj <- qcc(filtered_data$PartResistance, type = "xbar.one", plot = FALSE)
center_line <- qcc_obj$center
lcl <- qcc_obj$limits[1, "LCL"]
ucl <- qcc_obj$limits[1, "UCL"]
plot_df <- data.frame(Index = 1:length(filtered_data$PartResistance), PartResistance = filtered_data$PartResistance)
plot_df$is_violation <- factor(ifelse(plot_df$PartResistance < lcl | plot_df$PartResistance > ucl, "Violation", "In Control"))
plot_xbar_one <- ggplot(plot_df, aes(x = Index, y = PartResistance, color = is_violation)) +
  geom_line(aes(group = 1), color = "grey50", size = 0.5) +
  geom_point(size = 3, alpha = 0.7) +
  geom_hline(yintercept = center_line, linetype = "dashed", color = "#0072B2", size = 1, alpha = 0.7) +
  geom_hline(yintercept = lcl, linetype = "dotdash", color = "#D55E00", size = 1, alpha = 0.7) +
  geom_hline(yintercept = ucl, linetype = "dotdash", color = "#D55E00", size = 1, alpha = 0.7) +
  scale_color_manual(values = c("In Control" = "#009E73", "Violation" = "#CC79A7")) +
  labs(title = "Xbar Chart for Part Resistance (Machine 1)", x = "Observation Index", y = "Part Resistance") +
  theme_minimal() +
  theme(
    plot.background = element_rect(fill = "white"),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    legend.title = element_text(size = 16),
    legend.text = element_text(size = 14)
  )
