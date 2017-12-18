# ES6-Javascript


Section 2: The 'forEach' Helper 

Coding exercise 1: Moving away from For Loops:

      //Use forEach method to replicate the process/result
      function handlePosts() {
          var posts = [
            { id: 23, title: 'Daily JS News' },
            { id: 52, title: 'Code Refactor City' },
            { id: 105, title: 'The Brightest Ruby' }
          ];

          for (var i = 0; i < posts.length; i++) {
            savePost(posts[i]);
          }
      }

      //Utilize forEach to replicate above for loop result
      var posts = [{ id: 23, title: 'Daily JS News' },
            { id: 52, title: 'Code Refactor City' },
            { id: 105, title: 'The Brightest Ruby' }];

      posts.forEach(function(post){
          savePost(post);
      });
      
 Coding Exercise 2: Processing Values
 
      var images = [
        { height: 10, width: 30 },
        { height: 20, width: 90 },
        { height: 54, width: 32 }
      ];
      var areas = [];

      images.forEach(function(image) {
          areas.push(image.height*image.width);
      });
Section 3: The 'map' Finder

Coding Exercise 3: Plucking Values

  var images = [
    { height: '34px', width: '39px' },
    { height: '54px', width: '19px' },
    { height: '83px', width: '75px' },
  ];

  var heights = images.map(function(image){
      return image.height;
  });
  
Coding Exercise 4: Calculating Values with Map

  var trips = [
    { distance: 34, time: 10 },
    { distance: 90, time: 50 },
    { distance: 59, time: 25 }
  ];

  var speeds = trips.map(function(trip){
      return trip.distance/trip.time;
  });

Coding Exercise 5: Really Hard - Implementing Pluck

  function pluck(array, property) {
      var values = array.map(function(item){
          return item[property];
      });
      return values;
  }
