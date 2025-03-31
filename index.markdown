
test plot 2
![Burglary Calendar Plot]({{ site.baseurl }}/assets/burglary_calendar.png)

This calendar heatmap visualizes the distribution of reported burglaries in San Francisco over time. The color intensity represents the number of daily incidents, with darker green indicating higher numbers. Notable outlier days are specifically annotated to highlight unusual spikes in criminal activity.

test plot 3
<div style="width: 100%; height: 500px;">
  <iframe src="{{ site.baseurl }}/assets/crime_growth.html" frameborder="0" width="100%" height="100%"></iframe>
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
