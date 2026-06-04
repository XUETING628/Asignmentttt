
# R code for Process Capability Chart (Machine 1)
df_m1_filtered <- X005 %>%
  filter(Machine == 1, Temperature == 338, Pressure == 200)

if (nrow(df_m1_filtered) > 1) {
  qcc_obj_m1_pc <- qcc(df_m1_filtered$PartLength, type="xbar", sizes=5, plot=FALSE)
  pc_m1 <- process.capability(qcc_obj_m1_pc, spec.limits=c(45, 55), target=50)
  plot(pc_m1, lsl.col="#0072B2", usl.col="#D55E00", target.col="#009E73",
       x.lab="Part Length", y.lab="Density",
       title="Process Capability for PartLength (Machine 1, Temp 338, Press 200)",
       cex.text=1.2, cex.axis=1.2, cex.lab=1.2, cex.main=1.5)
}
