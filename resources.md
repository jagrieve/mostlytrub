---
layout: page
title: Resources
navigation: true
permalink: /resources/
googlemap: true
---

To the aspiring homebrewer, getting started can seem a little daunting. You know you'll eventually need a heap of equipment, but which bits are essential for your first batch?

To the established homebrewer, there can still be questions. Where can you find a 30L pot tall enough to fit your stove? Does anybody here sell camlocks? If you need 5L of mango pulp, do you have to make it yourself?

For a small island, we are fortunate to have two brick-and-mortar homebrew stores, [iBrew](http://www.ibrew.com.sg) and the recently relaunched [homebrewco.com.sg](http://www.homebrewco.com.sg/). We also have the [Singapore Homebrew Club](http://www.meetup.com/Singapore-Homebrew/messages/boards/), a fantastic way to meet like-minded brewers for help, advice and company over a pint. As of August 2014, [Thirsty](http://www.thirsty.com.sg/) are putting on a weekly homebrew sharing event on Fridays at their store in Liang Court.


A brewer's tour of Singapore
----------------------------

<div id="beer_map"></div>

<script>

  var homebrew_pois = [
    {
      name: "iBrew",
      coords: [1.313558, 103.771031],
      desc: "Raymond's homebrew store, closed on Monday and Tuesday.",
      address: "354 Clementi Avenue 2"
    },
    {
      name: "The Homebrew Co-op",
      coords: [1.2956678,103.8392231],
      desc: "The Homebrew Co-op, Neo's homebrew store.",
      address: "297A River Valley Road"
    },
    {
      name: "Lau Choy Seng",
      coords: [1.282594, 103.844488],
      desc: "Kitchen hardware store in Chinatown.",
      address: "23 Temple Street"
    },
    {
      name: "Sia Huat",
      coords: [1.282440, 103.844852],
      desc: "Catering supplies and kitchen hardware store in Chinatown.",
      address: "11 Temple Street"
    },
    {
      name: "5M",
      coords: [1.282695, 103.844388],
      desc: "Large glass bottles suitable for use as primary and secondary fermenters. There's another branch (called 5B) on Joo Chiat Rd.",
      address: "25 Trengganu St"
    },
    {
      name: "5B",
      coords: [1.3152486, 103.8981759],
      desc: "Large glass bottles suitable for use as primary and secondary fermenters. There's another branch (called 5M) on Temple St.",
      address: "46 Joo Chiat Rd"
    },
    {
      name: "Bottle shop",
      coords: [1.287428, 103.841892],
      desc: "Huge selection of bottles and lab glassware, including growlers.",
      address: "51 Chin Swee Rd, #02-107"
    },
    {
      name: "Smith Street Taps",
      coords: [1.282413, 103.843633],
      desc: "Draft beer in a hawker center! While strictly speaking this has nothing to do with homebrew, it's a favourite hangout for the local homebrew crowd. Closed on Mondays.",
      address: "Blk 335 Smith Street Chinatown Complex #02-062"
    },
    {
      name: "Thirsty",
      coords: [1.291289, 103.844604],
      desc: "Big selection of imported craft beers, and a new homebrew tasting night every Friday.",
      address: "177 River Valley Road #02-34, Liang Court"
    },
    {
      name: "Phoon Huat",
      coords: [1.307172, 103.789633],
      desc: "Massive baking supply chain, this is their newest outlet. Useful for all sorts, incuding jerry cans of fruit puree.",
      address: "Above Buona Vista MRT (stairs around the side)."
    },
    {
      name: "Bioplast Engineering",
      coords: [1.317964, 103.861413],
      desc: "Useful place to get CO2 cylinders refilled on the spot.",
      address: "Blk 22 Boon Keng Road, #01-23"
    }
  ];

  function initialize() {
    var map_canvas = document.getElementById('beer_map');
    
    var map_options = {
      center: new google.maps.LatLng(1.306114, 103.844735),
      zoom: 13,
      mapTypeId: google.maps.MapTypeId.ROADMAP
    }
    
    var map = new google.maps.Map(map_canvas, map_options);
    
    var marker = [];
    var infowindow = [];
    for (var i = 0; i < homebrew_pois.length; i++) {
      var poi = homebrew_pois[i];
      var latLng = new google.maps.LatLng(poi.coords[0], poi.coords[1]);
      marker[i] = new google.maps.Marker({
        position: latLng,
        title: poi.name,
        map: map,
      });
      infowindow[i] = new google.maps.InfoWindow({
        content: '<h2>'+poi.name+'</h2><p class="address">'+poi.address+'</p><p>'+poi.desc+'</p>'
      });
      google.maps.event.addListener(marker[i], 'click', function(ii) {
        return function() {
          infowindow[ii].open(map,marker[ii]);
        }
        }(i));
    }
  }
  
  google.maps.event.addDomListener(window, 'load', initialize);
</script>

