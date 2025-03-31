The following case study is based on police department incident reports obtained from DataSF, a data archive managed by San Francisco City and County departments. Combined, they contain over three million reports for various crimes spanning from 2003 to 2025, including date, time, location, crime category, and police district. After merging the two datasets, we looked for trends over time based on these variables, particularly as they pertained to the COVID-19 pandemic.  

We found that, overall, crime rates sharply declined as lockdown mandates were imposed in the city in March of 2020. From then on, we see a gradual increase in daily reports through the rest of the year. We can also see some noticeable daily highs, such as during the protests and ensuing riots at the end of May following the death of George Floyd.  

George Floyd was an African-American man murdered at the hands of a Minneapolis police officer in May of 2020. His death prompted large-scale demonstrations across the United States, protesting racially motivated police brutality. Although these protests were overwhelmingly peaceful, there were many instances of vandalism, looting, and rioting by demonstrators. This would explain the increase in arrests in San Francisco during this time period.  



Test Plot 1

<div style="width: 100%; height: 500px;">
  <iframe src="{{ site.baseurl }}/assets/burglary_heatmap.html" frameborder="0" width="100%" height="100%"></iframe>
</div>


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
