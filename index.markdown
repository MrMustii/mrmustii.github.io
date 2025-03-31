---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

---
---

Test Plot 1

<div style="width: 100%; height: 500px;">
  <iframe src="{{ site.baseurl }}/assets/burglary_heatmap.html" frameborder="0" width="100%" height="100%"></iframe>
</div>

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
    <option value="#">--Select a category--</option>
    <option value="https://mrmustii.github.io/assets/calplots/assault_2020_calplot.png">Assault</option>
    <option value="https://mrmustii.github.io/assets/calplots/burglary_2020_calplot.png">Burglary</option>
    <option value="https://mrmustii.github.io/assets/calplots/drug_narcotic_2020_calplot.png">Drugs/Narcotics</option>
    <option value="https://mrmustii.github.io/assets/calplots/larceny_theft_2020_calplot.png">Larceny/Theft</option>
    <option value="https://mrmustii.github.io/assets/calplots/prostitution_2020_calplot.png">Prostitution</option>
    <option value="https://mrmustii.github.io/assets/calplots/robbery_2020_calplot.png">Robbery</option>
    <option value="https://mrmustii.github.io/assets/calplots/stolen_property_2020_calplot.png">Stolen Property</option>
    <option value="https://mrmustii.github.io/assets/calplots/vandalism_2020_calplot.png">Vandalism</option>
    <option value="https://mrmustii.github.io/assets/calplots/vehicle_theft_2020_calplot.png">Vehicle Theft</option>
    <option value="https://mrmustii.github.io/assets/calplots/weapon_laws_2020_calplot.png">Weapon Laws</option>
    <option value="https://mrmustii.github.io/assets/calplots/other_offenses_2020_calplot.png">Other Offenses</option>
  </select>
</div>

<div id="crime-category-image" style="margin-top: 20px;">
  <img src="#" alt="Select a category to view the plot" style="width: 100%; max-height: 500px; display: none;" id="crime-image">
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
