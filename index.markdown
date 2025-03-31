The following case study is based on police department incident reports obtained from DataSF, a data archive managed by San Francisco City and County departments. Combined, they contain over three million reports for various crimes spanning from 2003 to 2025, including date, time, location, crime category, and police district. After merging the two datasets, we looked for trends over time based on these variables, particularly as they pertained to the COVID-19 pandemic.  

We found that, overall, crime rates sharply declined as lockdown mandates were imposed in the city in March of 2020. From then on, we see a gradual increase in daily reports through the rest of the year. We can also see some noticeable daily highs, such as during the protests and ensuing riots at the end of May following the death of George Floyd. 

<div style="width: 100%; height: 500px;">
  <iframe src="{{ site.baseurl }}/assets/crime_growth_2020.html" frameborder="0" width="100%" height="100%"></iframe>
</div> 

George Floyd was an African-American man murdered at the hands of a Minneapolis police officer in May of 2020. His death prompted large-scale demonstrations across the United States, protesting racially motivated police brutality. Although these protests were overwhelmingly peaceful, there were many instances of vandalism, looting, and rioting by demonstrators. This would explain the increase in arrests in San Francisco during this time period.  

If we break down the crime types that were reported during this time, we can see drastic changes in the distribution of our different categories. The bar graph below shows the percent change from 2017 for each category of crime.  

<div>
  <label for="crime-category-selector">Choose a crime category:</label>
  <select id="crime-category-selector" onchange="updateImage(this.value);">
    <option value="{{ site.baseurl }}/assets/calplots/all_crimes_2020_calplot.png" selected>ALL CRIMES OF 2020</option>
    <option value="{{ site.baseurl }}/assets/calplots/assault_2020_calplot.png">Assault</option>
    <option value="{{ site.baseurl }}/assets/calplots/burglary_2020_calplot.png">Burglary</option>
    <option value="{{ site.baseurl }}/assets/calplots/drug_narcotic_2020_calplot.png">Drugs/Narcotics</option>
    <option value="{{ site.baseurl }}/assets/calplots/larceny_theft_2020_calplot.png">Larceny/Theft</option>
    <option value="{{ site.baseurl }}/assets/calplots/prostitution_2020_calplot.png">Prostitution</option>
    <option value="{{ site.baseurl }}/assets/calplots/robbery_2020_calplot.png">Robbery</option>
    <option value="{{ site.baseurl }}/assets/calplots/stolen_property_2020_calplot.png">Stolen Property</option>
    <option value="{{ site.baseurl }}/assets/calplots/vandalism_2020_calplot.png">Vandalism</option>
    <option value="{{ site.baseurl }}/assets/calplots/vehicle_theft_2020_calplot.png">Vehicle Theft</option>
    <option value="{{ site.baseurl }}/assets/calplots/weapon_laws_2020_calplot.png">Weapon Laws</option>
    <option value="{{ site.baseurl }}/assets/calplots/other_offenses_2020_calplot.png">Other Offenses</option>
    <option value="{{ site.baseurl }}/assets/burglary_calendar.png">Burglary (2018 - 2024)</option>
  </select>
</div>

<div id="crime-category-image" style="margin-top: 20px;">
  <img src="{{ site.baseurl }}/assets/calplots/all_crimes_2020_calplot.png" alt="ALL CRIMES OF 2020" style="width: 100%;" id="crime-image">
</div>

We can see that the prevalence of burglaries skyrocketed starting in 2020, marking a nearly 60% increase from 2017. Similarly, vehicle theft had increased by nearly 40% since 2017. On the other hand, prostitution reports were down over 80%, and stolen property crimes were down 20%.  

Let’s take a closer look at burglaries in the city following the murder of George Floyd and as protests began.

The heat map illustrates the concentration of reported burglary crimes in the days leading up to the protests, during the events, and in the aftermath. During the protests, a significant increase in criminal activity was observed.  

This trend is particularly noteworthy because it shows neighborhoods such as Chinatown or Tenderloin which is one of San Francisco's most densely populated neighborhoods. According to data from the *Statistical Atlas*, the Tenderloin neighborhood has the highest population density in the city, with approximately **129,000 people per square mile**, significantly higher than the citywide average of **18,131 people per square mile**[^1].  

Additionally, the Tenderloin reports a median household income of **$24,400**, which is considerably lower than San Francisco’s overall median household income of **$87,738**[^2]. Moreover, Tenderloin PD and central PD (which has the jurisdiction north of Tenderloin) alone reported more than half of burglaries on May 30th.  

These socioeconomic conditions, high population density and low  income, may contribute to the disproportionate concentration of crimes during the protests. Research has shown that urban areas with lower median income levels tend to experience higher rates of certain types of crime[^3].  These findings suggest that socioeconomically disadvantaged neighborhoods were disproportionately impacted by the unrest, with higher rates of burglary observed in areas characterized by lower median household incomes and higher population densities.  


<div style="width: 100%; height: 500px;">
  <iframe src="{{ site.baseurl }}/assets/burglary_heatmap_george_floyd.html" frameborder="0" width="100%" height="100%"></iframe>
</div>

###### Conclusion  

Ultimately, historically underserved communities in San Francisco were disproportionately affected by the events of 2020, both economically and socially. As restrictions were imposed, the relative rates of burglaries and vehicle thefts skyrocketed, while other categories of crime fell in frequency. The unrest following George Floyd’s murder further cemented this trend, as instances of looting and vandalism led to a surge in burglary reports, particularly in the Tenderloin and Central police districts. These patterns underscore the severity of 2020's impact on the neighborhoods of San Francisco’s most vulnerable communities.

###### References
[^1]: [Statistical Atlas – Population Density in San Francisco](https://statisticalatlas.com/place/California/San-Francisco/Population)  
[^2]: [U.S. Census Bureau QuickFacts: San Francisco](https://www.census.gov/quickfacts/fact/table/sanfranciscocitycalifornia)  
[^3]: [The Relationship Between Poverty and Crime](https://www.northwestcareercollege.edu/blog/the-relationship-between-poverty-and-crime/)



<script>
  function updateImage(imageUrl) {
    const imgElement = document.getElementById('crime-image');
    if (imageUrl === "#") {
      imgElement.style.display = "none";
    } else {
      imgElement.src = imageUrl;
      imgElement.style.display = "block";
    }
  }
</script>
