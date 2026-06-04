
# R code for Process Capability Chart (Machine 2)
df_m2_filtered <- X005 %>%
  filter(Machine == 2, Temperature == 338, Pressure == 200)

if (nrow(df_m2_filtered) > 1) {
  qcc_obj_m2_pc <- qcc(df_m2_filtered$PartLength, type="xbar", sizes=5, plot=FALSE)
  pc_m2 <- process.capability(qcc_obj_m2_pc, spec.limits=c(45, 55), target=50)
  plot(pc_m2, lsl.col="#0072B2", usl.col="#D55E00", target.col="#009E73",
       x.lab="Part Length", y.lab="Density",
       title="Process Capability for PartLength (Machine 2, Temp 338, Press 200)",
       cex.text=1.2, cex.axis=1.2, cex.lab=1.2, cex.main=1.5)
}
