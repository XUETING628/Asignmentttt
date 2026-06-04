
# R code for X-bar Control Chart (Machine 3)
df_m3_filtered <- X005 %>%
  filter(Machine == 3, Temperature == 338, Pressure == 200)

control_chart_m3 <- qcc(df_m3_filtered$PartLength, type="xbar", nsigmas=3, sizes=5,
                        title="X-bar Control Chart for PartLength (Machine 3, Temp 338, Press 200)",
                        ylab="Part Length")
plot(control_chart_m3)
