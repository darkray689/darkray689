<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Інтерактивна карта міграції</title>
  <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
  <style>
    /* Встановлення розмірів карти */
    #map {
      height: 600px;
      width: 100%;
    }
  </style>
</head>
<body>

<h3>Інтерактивна карта міграції</h3>
<div id="map"></div>

<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
<script>
  // Ініціалізація карти
  var map = L.map('map').setView([48.3794, 31.1656], 6); // Центр карти - Україна

  // Додавання базової карти OpenStreetMap
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
  }).addTo(map);

  // Дані для маркерів (приклад для зовнішньої міграції)
  var locations = [
    {name: 'Німеччина', lat: 51.1657, lng: 10.4515, population: '1,000,000'},
    {name: 'Польща', lat: 51.9194, lng: 19.1451, population: '900,000'}
    // Додавайте інші країни або області, якщо потрібно
  ];

  // Додавання маркерів на карту
  locations.forEach(function(location) {
    var marker = L.marker([location.lat, location.lng]).addTo(map);
    marker.bindPopup('<h4>' + location.name + '</h4><p>Переміщено осіб: ' + location.population + '</p>');
  });
</script>

</body>
</html>

--->
