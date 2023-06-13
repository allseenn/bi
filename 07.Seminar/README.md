Календарь = 
ADDCOLUMNS(
CALENDAR(MIN('Маркетинговые данные'[Date]),Max('Маркетинговые данные'[Date])),
"День",FORMAT([Date], "DD.MM.YYYY"),
"Неделя",FORMAT(MAX( DATE(YEAR([Date]),1,1), [Date]-WEEKDAY([Date],2) ),"DD.MMM") & "-" & FORMAT(MIN( DATE(YEAR([Date]),12,31), [Date]+7-WEEKDAY([Date],2) ),"DD.MMM"),
"Месяц",FORMAT([Date], "MMMM YYYY"),
"Год",YEAR([Date]),
"День недели",FORMAT([Date], "DDDD"),
"Месяц сортировка", FORMAT([Date], "YYYYMM"),
"Номер недели",WEEKNUM([Date], 2),

"День сортировка", FORMAT([Date],"YYYYMMDD"),
"Имя месяца", FORMAT([Date],"MMM"),
"Месяц номер", MONTH([Date])
)