# ROC-curve-and-best-cutoff
ls()
 [1] "abl"  "age"  "cr"   "data" "id"   "ldh"  "mods" "reg"  "sex"  "xlab"
data[1:3,]
  id sex age    ldh    cr  abl mods
1  1   f  65  299.3  47.1 34.4    1
2  2   m  40 2036.0 395.1 25.9    1
3  3   m  78  881.0  89.4 39.1    1
 library(Daim)
roc(data[,4],data[,7],"1")->r.ldh
plot(r.ldh)
roc(data[,4:6],data[,7],"1")->r3
plot(r3)
summary(r3)
ldh                               cr                               
Number of cut-points: 104.0000    Number of cut-points:  71.0000   
 Best cut-point      : 299.3000    Best cut-point      : 107.0000   
 Sensitivity         :   0.2353    Sensitivity         :   0.0471   
 Specificity         :   0.9643    Specificity         :   0.6786   
 AUC                 :   0.9034    AUC                 :   0.7998   
 abl                             
 Number of cut-points: 85.0000   
 Best cut-point      : 17.9000   
 Sensitivity         :  1.0000   
 Specificity         :  1.0000   
 AUC                 :  0.1483   
par(mfrow=c(2,2))
data[1,]
  id sex age   ldh   cr  abl mods
1  1   f  65 299.3 47.1 34.4    1
 roc(data[,4],data[,7],"1")->r.ldh
 roc(data[,5],data[,7],"1")->r.cr
 roc(data[,6],data[,7],"0")->r.abl
 plot(r.ldh,main="ldh")
 plot(r.cr,main="cr")
 plot(r.abl,main="abl")
