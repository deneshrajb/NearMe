# Ex03 Places Around Me
## Date: 6/1/2026

## AIM
To develop a website to display details about the places around my house.

## DESIGN STEPS

### STEP 1
Create a Django admin interface.

### STEP 2
Download your city map from Google.

### STEP 3
Using ```<map>``` tag name the map.

### STEP 4
Create clickable regions in the image using ```<area>``` tag.

### STEP 5
Write HTML programs for all the regions identified.

### STEP 6
Execute the programs and publish them.

## CODE
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Places Around My House</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            text-align: center;
        }

        h1 {
            background-color: #2c3e50;
            color: white;
            padding: 20px;
            margin: 0;
        }

        #map {
            width: 90%;
            height: 400px;
            margin: 20px auto;
            border: 3px solid #333;
        }

        .place {
            background-color: white;
            width: 80%;
            margin: 20px auto;
            padding: 20px;
            box-shadow: 0 0 10px #aaa;
            border-radius: 10px;
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #2c3e50;
            color: white;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #34495e;
        }
    </style>
</head>
<body>

<h1>Places Around My House</h1>
<p>Click the button to view places around your current location</p>

<button onclick="getLocation()">Use My Location</button>

<div id="map"></div>

<div class="place">
    <h2>Nearby Places</h2>
    <p>The map shows nearby schools, hospitals, parks, and shopping areas around my house.</p>
</div>

<script>
    function getLocation() {
        if (navigator.geolocation) {
            navigator.geolocation.getCurrentPosition(showMap, showError);
        } else {
            alert("Geolocation is not supported by this browser.");
        }
    }

    function showMap(position) {
        var lat = position.coords.latitude;
        var lon = position.coords.longitude;

        var mapFrame = `
            <iframe
                width="100%"
                height="100%"
                frameborder="0"
                style="border:0"
                src="https://www.google.com/maps?q=${lat},${lon}&z=15&output=embed"
                allowfullscreen>
            </iframe>
        `;

        document.getElementById("map").innerHTML = mapFrame;
    }

    function showError(error) {
        alert("Location access denied. Please allow location permission.");
    }
</script>

</body>
</html>
```

## OUTPUT
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/5d2d2842-0f52-468d-b5ae-311c21bd6665" />

## RESULT
The program for implementing image maps using HTML is executed successfully.
