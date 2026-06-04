
# R code for X-bar Control Chart (Machine 2)
df_m2_filtered <- X005 %>%
  filter(Machine == 2, Temperature == 338, Pressure == 200)

control_chart_m2 <- qcc(df_m2_filtered$PartLength, type="xbar", nsigmas=3, sizes=5,
                        title="X-bar Control Chart for PartLength (Machine 2, Temp 338, Press 200)",
                        ylab="Part Length")
plot(control_chart_m2)
