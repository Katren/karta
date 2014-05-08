karta
=====
<html>
   <head>
      <meta charset="utf-8">
      <title> 
         Пример 1 
      </title>
      <script src="http://api-maps.yandex.ru/2.0-stable/?load=package.standard&lang=ru_RU" type="text/javascript"></script>
   </head>
   <body>
      <div id="map" style="width: 800px; height: 600px"></div>
   </body>
   <h1>
   СУПЕР КАРТА!
   <h1>
   <script type="text/javascript">
      ymaps.ready(init);
      var myMap;
      var myPlacemark;
      var myPlace;
      
      function init() {
      myMap = new ymaps.Map("map", {
          center: [56.86, 60.64],
          zoom: 14
      });
      myPlacemark = new ymaps.Placemark([56.841525, 60.61392], {
          content: 'Универ!',
          balloonContent: 'Мы тут'
      });
      
      myMap.geoObjects.add(myPlacemark);
      
      myPlace = new ymaps.Placemark([56.823871, 60.581497], {
      content: 'Дом',
      balloonContent: 'Мы тут'
      });
      
      myMap.geoObjects.add(myPlace);
      var myControlGroup = new ymaps.control.Group({
      items: [
      new ymaps.control.Button('Первый'),
      new ymaps.control.Button('Второй'),
      new ymaps.control.Button('Расчет окончен')
      ]
      }, {selectOnClick: false});
      
      myControlGroup.events.add(['click'], function (e) {
      alert(e.get('target').data.get('content'));
      });
      myMap.controls.add(myControlGroup);
      
      //myMap.behaviors.enable('ruler');
      myMap.controls.add(new ymaps.control.ZoomControl());
      myMap.controls.add('searchControl');
      }
      
   </script>
   </body> 
</html>
