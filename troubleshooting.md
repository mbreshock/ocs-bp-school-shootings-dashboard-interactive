# Troubleshooting notes

## Learnr and Gradethis rendering issues

Rendering issues were fixed when the following code chunk involving datatables was commented out: 

```{r}
DT_table <-
    shooting_data %>% 
    dplyr::select(Date,
                  School,
                  City,
                  State,
                  `Killed (includes shooter)`,
                  `Narrative (Detailed Summary/ Background)`) %>%
    rename("Deaths" = `Killed (includes shooter)`) %>%
    rename("Narrative" = `Narrative (Detailed Summary/ Background)`)

DT::datatable(DT_table)
```

This chunk is found on lines 1285-1298 in the current index.Rmd file of this repository version and on lines 1237-1250 in the index.Rmd file of the [static repository on GitHub](https://github.com/opencasestudies/ocs-bp-school-shootings-dashboard/blob/master/index.Rmd).
(As of 2/22/2022)