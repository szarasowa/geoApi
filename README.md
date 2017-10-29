# geoApi


            function getCoordinates() {
                navigator.geolocation.getCurrentPosition(updateLocation, handleLocationError);
            }

            function updateLocation(position) {
                var latitude = position.coords.latitude;
                var longitude = position.coords.longitude;
                var accuracy = position.coords.accuracy;
                var timestamp = position.timestamp;

                document.getElementById('latitude').innerHTML = latitude;
                document.getElementById('longitude').innerHTML = longitude;
                document.getElementById('accuracy').innerHTML = accuracy;
                document.getElementById('timestamp').innerHTML = timestamp;

                // developers.google.com
                var uluru = {lat: latitude, lng: longitude};
                var map = new google.maps.Map(document.getElementById('map'), {
                zoom: 10,
                center: uluru
                });
                var marker = new google.maps.Marker({
                position: uluru,
                map: map
                });
            }

---
test https://szarasowa.ovh/geoAPI/index.html
