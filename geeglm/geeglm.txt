# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Fit Generalized Estimating Equations (GEE) Use geeglm (geepack) With R Software
install.packages("geepack")
library("geepack")
geeglm = read.csv("https://raw.githubusercontent.com/timbulwidodostp/geeglm/main/geeglm/geeglm.csv",sep = ";")
# Estimation Fit Generalized Estimating Equations (GEE) Use geeglm (geepack) With R Software
geeglm$Cu <- as.factor(geeglm$Cu)
geeglm_model <- formula(Weight ~ Cu * (Time + I(Time^2) + I(Time^3)))
geeglm <- geeglm(geeglm_model, data=geeglm, id=Pig, family=poisson("identity"), corstr="ar1")
coef(geeglm)
vcov(geeglm)
summary(geeglm)
coef(summary(geeglm))
# Fit Generalized Estimating Equations (GEE) Use geeglm (geepack) With R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished