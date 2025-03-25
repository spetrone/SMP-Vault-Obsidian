# Sites
- started with 431 before filtering
- ended with 59 sites and then 50, after filtering for the lichen protocol 


### Quadrants
- 228 quadrants - then 200 quadrants after filtering for the lichen protocol


### Lichen Species
- 169 unique lichen species


# 1. Regression
### Simpson Index:

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| REML criterion at convergence: 1147.2<br><br>Scaled residuals: <br>    Min      1Q  Median      3Q     Max <br>-4.0753 -0.5887  0.0362  0.5944  2.3505 <br><br>Random effects:<br> Groups    Name        Variance Std.Dev.<br> ABMI_Site (Intercept) 12.68    3.561   <br> Residual              12.97    3.601   <br>Number of obs: 199, groups:  ABMI_Site, 50<br><br>Fixed effects:<br>                  Estimate Std. Error      df t value Pr(>\|t\|)    <br>(Intercept)         19.895      1.008 153.329  19.736   <2e-16 ***<br>div_df$struct_ind    7.371      3.266 196.938   2.257   0.0251 *  <br>---<br>Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1<br><br>Correlation of Fixed Effects:<br>            (Intr)<br>dv_df$strc_ -0.828 |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

### 2. Shannon Index

REML criterion at convergence: 1169.1

Scaled residuals: 
    Min      1Q  Median      3Q     Max 
-4.3154 -0.5908  0.0153  0.6044  2.1784 

Random effects:
 Groups    Name        Variance Std.Dev.
 ABMI_Site (Intercept) 13.90    3.728   
 Residual              14.57    3.816   
Number of obs: 199, groups:  ABMI_Site, 50

Fixed effects:
                  Estimate Std. Error      df t value Pr(>|t|)    
(Intercept)         22.088      1.063 153.343  20.771   <2e-16 ***
div_df$struct_ind    7.686      3.453 196.982   2.226   0.0272 *  
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Correlation of Fixed Effects:
            (Intr)
dv_df$strc_ -0.830

### 3. Species Richness
REML criterion at convergence: 1205.7

Scaled residuals: 
    Min      1Q  Median      3Q     Max 
-4.3929 -0.5257  0.0005  0.6264  2.0413 

Random effects:
 Groups    Name        Variance Std.Dev.
 ABMI_Site (Intercept) 16.56    4.069   
 Residual              17.59    4.194   
Number of obs: 199, groups:  ABMI_Site, 50

Fixed effects:
                  Estimate Std. Error      df t value Pr(>|t|)
(Intercept)         24.715      1.165 153.332   21.21   <2e-16
div_df$struct_ind    8.071      3.789 196.995    2.13   **0.0344**
                     
(Intercept)       ***
div_df$struct_ind *  
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Correlation of Fixed Effects:
            (Intr)
dv_df$strc_ -0.831


### 4. Abundance
REML criterion at convergence: 1627

Scaled residuals: 
     Min       1Q   Median       3Q      Max 
-2.95534 -0.62383 -0.08124  0.52003  2.92305 

Random effects:
 Groups    Name        Variance Std.Dev.
 ABMI_Site (Intercept) 183.2    13.54   
 Residual              139.6    11.82   
Number of obs: 199, groups:  ABMI_Site, 50

Fixed effects:
                  Estimate Std. Error      df t value Pr(>|t|)
(Intercept)         54.099      3.504 151.794   15.44   <2e-16
div_df$struct_ind    6.710     11.001 194.494    0.61    **0.543**
                     
(Intercept)       ***
div_df$struct_ind    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Correlation of Fixed Effects:
            (Intr)
dv_df$strc_ -0.803


## 2. Structural Index PCA
Importance of components:
                          PC1    PC2    PC3    PC4     PC5     PC6     PC7     PC8
Standard deviation     1.9390 1.1479 1.0911 0.9611 0.76698 0.63697 0.60025 0.55879
Proportion of Variance 0.4178 0.1464 0.1323 0.1026 0.06536 0.04508 0.04003 0.03469
Cumulative Proportion  0.4178 0.5642 0.6965 0.7991 0.86445 0.90953 0.94956 0.98426
                           PC9
Standard deviation     0.37642
Proportion of Variance 0.01574
Cumulative Proportion  1.00000


### CC - structural attributes & diversity indices
(Pearson's product-moment correlation)

PC1 - significance:
data:  cca_result$scores$xscores[, 1] and cca_result$scores$yscores[, 1]
t = 5.4966, df = 197, **p-value = 1.189e-07**
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 0.2376144 0.4794263
sample estimates:
      cor 
0.3646527

PC2 - significance:
data:  cca_result$scores$xscores[, 2] and cca_result$scores$yscores[, 2]
t = 3.6156, df = 197, **p-value = 0.0003806**
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 0.1143329 0.3755166
sample estimates:
      cor 
0.2494559

#### Scores:
             [,1]      [,2]      [,3]
SR      0.5201389 0.7369020 0.4317765
Shannon 0.5718134 0.5997946 0.5597106
Simpson 0.6381841 0.4610196 0.6165890
> cca_result$scores$corr.Y.yscores[,1:3]
                   [,1]        [,2]       [,3]
DBHq         -0.1969220  0.09857944 0.31275577
DBH_sd       -0.3137614  0.42841247 0.52199217
height_sd    -0.1999641  0.40686276 0.28233035
quad_vol     -0.2722538 -0.11849202 0.46167720
DC            0.5479787  0.14301124 0.21398448
snag_dbh      0.4328244 -0.04632221 0.39921521
ddd          -0.1367118  0.45699701 0.19967503
tree_sh_ind   0.1086986  0.13593598 0.62470487
regen_sh_ind  0.4872207  0.53803649 0.05034483



### 4.  Species Composition PCoA
summary(pcoa_data)
      PC1               PC2           StructuralIndex 
 Min.   :-2.9273   Min.   :-1.05433   Min.   :0.0000  
 1st Qu.:-1.0242   1st Qu.:-0.49379   1st Qu.:0.1755  
 Median : 0.3430   Median :-0.04033   Median :0.2496  
 Mean   : 0.0000   Mean   : 0.00000   Mean   :0.2559  
 3rd Qu.: 0.9706   3rd Qu.: 0.39363   3rd Qu.:0.3195  
 Max.   : 2.5170   Max.   : 1.59575   Max.   :0.6015
#### Significance:
Pearson's product-moment correlation

First axis
data:  site_scores[, 1] and lichen_dist_df$struct_ind
t = 9.6558, df = 197, **p-value < 2.2e-16**
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 0.4642900 0.6542887
sample estimates:
      cor 
**0.5667785**

Second axis:
Pearson's product-moment correlation

data:  site_scores[, 2] and lichen_dist_df$struct_ind
t = 1.476, df = 197, p-value = 0.1415
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 -0.03501191  0.24018330
sample estimates:
      cor 
0.1045873



## 5. CCA - Species Composition and Structural Index


cca(formula = lichen_matrix ~ lichen_dist_df$struct_ind) 

Partitioning of scaled Chi-square:
              Inertia Proportion
Total         4.23402    1.00000
Constrained   0.09553    0.02256
Unconstrained 4.13848    0.97744

### Significance:
Pearson's product-moment correlation

data:  site_scores[, 1] and struct_ind
t = 9.6558, df = 197, p-value < 2.2e-16
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 0.4642900 0.6542887
sample estimates:
      cor 
0.5667785