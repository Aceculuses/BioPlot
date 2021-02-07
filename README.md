# BioPlot

# Volcano pot

Input dataset

|   LFC    |    p value  |
|----------|-------------|
|   2.31   |    0.0015   |
|   0.34   |    0.86     |
|   2.07   |    0.35     |
|   ...    |    ...      |

```
# Obtain logical vector regarding whether padj values are less than 0.05
threshold <- vol.res$pval < 0.05 

# Determine the number of TRUE values
length(which(threshold))

ggplot(vol.res) +
  geom_point(aes(x=Mval, y=-log10(pval), colour=threshold)) +
  ggtitle("CD34plusB sigPeaks") +
  xlab("log2 fold change") + 
  ylab("-log10 p-value") +
  #scale_y_continuous(limits = c(0,50)) +
  theme(legend.position = "none",
        plot.title = element_text(size = rel(1.5), hjust = 0.5),
        axis.title = element_text(size = rel(1.25)))
```
![image](https://github.com/Aceculuses/BioPlot/blob/main/CD34plusB.sigPeaks.volcano.png)




