---
title: "Blog: Energy Transformation"
description: ""
featured_image: ""
---

<style>
.page-header {
  background-image: url("https://suncore.com.mx/wp-content/uploads/2020/10/solar-energy-5622969_1920.jpg");
  background-size: cover;
  background-position: top;
  background-repeat: no-repeat;
  padding: 150px 0;
}
.page-header h1 {
  color: white;
  text-align: center;
  text-shadow: 0 2px 10px rgba(0,0,0,0.5);
  font-size: 49px;
  margin: 0;
}

.article-card {
  border: 1px solid #ccc;
  padding: 15px;
  border-radius: 8px;
  margin-bottom: 85px;
}

.filter-container {
  margin: 20px 0;
  display: flex;
  gap: 10px;
  align-items: center;
}

</style>

<div class="page-header">
  <h1>Blog: Energy Transformation</h1>
</div>

<blockquote>
Pick up the Articles more interesting for you about Energy Transition!
</blockquote>
<!-- FILTER SECTION -->
<div class="filter-container" style="margin-bottom: 20px; text-align: left;">
  <label for="categoryFilter" style="font-weight:bold; margin-right:10px;">Filter by Category:</label>
  <select id="categoryFilter" style="padding: 7px 12px; border-radius: 6px; border:1px solid #ccc;">
    <option value="none">Select Topic</option>
    <option value="gas">Natural Gas</option>
    <option value="solar">Solar Energy</option>
    <option value="wind">Wind Energy</option>
    <option value="bio">Bioenergy</option>
    <option value="hydrogen">Hydrogen</option>
  </select>
</div>

<!-- HIDDEN ARTICLES (No longer displayed) -->
<div id="articlesContainer" style="display:none;">
  <div class="article-card" data-category="gas"></div>
  <div class="article-card" data-category="solar"></div>
  <div class="article-card" data-category="wind"></div>
  <div class="article-card" data-category="bio"></div>
  <div class="article-card" data-category="hydrogen"></div>
</div>

<!-- CATEGORY INFO BOX -->
<div id="categoryInfo" style="margin-top:25px; padding:20px; border-radius:8px; background:#f5f5f5; display:none;"></div>

<script>
const filterSelect = document.getElementById("categoryFilter");
const infoBox = document.getElementById("categoryInfo");

// Información detallada por categoría
const categoryDetails = {
  "gas": `
    <h3>Natural Gas</h3>
    <p>Natural gas is a highly efficient energy source used in combined-cycle thermoelectric plants. 
    It produces fewer emissions than coal and serves as a bridge fuel in the transition to renewable energy.</p>
  `,
  "solar": `
    <h3>Solar Energy</h3>
    <p>Solar energy uses photovoltaic (PV) technology to convert sunlight into electricity. 
    It is one of the fastest-growing clean energy sources and requires minimal maintenance.</p>
  `,
  "wind": `
    <h3>Wind Energy</h3>
    <p>Wind turbines capture kinetic wind energy and convert it into electrical power. 
    Offshore wind installations achieve the highest energy output due to stronger, consistent winds.</p>
  `,
  "bio": `
    <h3>Bioenergy</h3>
    <p>Bioenergy uses organic matter—such as agricultural waste, wood, or biogas—to produce electricity. 
    It supports circular energy systems and reduces landfill waste.</p>
  `,
  "hydrogen": `
    <h3>Hydrogen Energy</h3>
    <p>Green hydrogen, produced with renewable electricity, can store large amounts of clean energy and 
    power vehicles, industries, and fuel cells with zero emissions.</p>
  `
};

// Evento del filtro
filterSelect.addEventListener("change", function() {
  const selected = this.value;

  if (selected === "none") {
    infoBox.style.display = "none";
    infoBox.innerHTML = "";
    return;
  }

  infoBox.style.display = "block";
  infoBox.innerHTML = categoryDetails[selected];
});
</script>

