
# R code for X-bar Control Chart (Machine 1)
df_m1_filtered <- X005 %>%
  filter(Machine == 1, Temperature == 338, Pressure == 200)

control_chart_m1 <- qcc(df_m1_filtered$PartLength, type="xbar", nsigmas=3, sizes=5,
                        title="X-bar Control Chart for PartLength (Machine 1, Temp 338, Press 200)",
                        ylab="Part Length")
plot(control_chart_m1)
