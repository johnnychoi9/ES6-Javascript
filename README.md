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

Section 4: The 'filter' Helper

Coding Exercise 6: Filtering Values

      var numbers = [15, 25, 35, 45, 55, 65, 75, 85, 95];

      var filteredNumbers = numbers.filter(function(number){
          return number > 50;
      });
            
Coding Exercise 7: Handling Permissions with Filter

      var users = [
       { id: 1, admin: true },  
       { id: 2, admin: false },
       { id: 3, admin: false },
       { id: 4, admin: false },
       { id: 5, admin: true },
      ];

      var filteredUsers = users.filter(function(user){
          return user.admin;
      });
            
Coding Exercise 8: Challenging! Implementing 'reject'

      function reject(array, iteratorFunction) {
        return array.filter(function(object){
            return !iteratorFunction(object);
        });
      }
            
Coding Exercise 9:

      var users = [
        { id: 1, admin: false },
        { id: 2, admin: false },
        { id: 3, admin: true }
      ];

      var admin = users.find(function(user){
          return user.admin === true;
      });
      
      
Coding Exercise 10: What's your Balance

      var accounts = [
        { balance: -10 },
        { balance: 12 },
        { balance: 0 }
      ];

      var account = accounts.find(function(account){
          return account.balance === 12;
      });
      
 Coding Exercise 11: Really Challenging: Custom findWhere helper
 
       function findWhere(array, criteria) {

        var property = Object.keys(criteria)[0];
        var result = array.find(function(object){
            return object[property] === criteria[property];
        });
        return result;
      }
      
Coding Exercise 12: Finding Submitted Users
 
       var users = [
        { id: 21, hasSubmitted: true },
        { id: 62, hasSubmitted: false },
        { id: 4, hasSubmitted: true }
      ];

      var hasSubmitted = users.every(function(user){
          return user.hasSubmitted;
      });
      
Coding Exercise 13: In Progress Network Requests

      var requests = [
        { url: '/photos', status: 'complete' },
        { url: '/albums', status: 'pending' },
        { url: '/users', status: 'failed' }
      ];

      var inProgress = requests.some(function(request){
          return request.status;
      });
      
Coding Exercise 14: Distance Traveled

      var trips = [{ distance: 34 }, { distance: 12 } , { distance: 1 }];

      var totalDistance = trips.reduce(function(sum, trip){
          return sum + trip.distance;

      }, 0);

Coding Exercise 15: Reducing Properties

      var desks = [
        { type: 'sitting' },
        { type: 'standing' },
        { type: 'sitting' },
        { type: 'sitting' },
        { type: 'standing' }
      ];

      var deskTypes = desks.reduce(function(previous, desk) {
          if (desk.type === 'sitting') {
              ++previous.sitting;
          }
          if (desk.type === 'standing') {
              ++previous.standing;
          }
          return previous;
      }, { sitting: 0, standing: 0 });

Coding Exercise 16: Hardmode: Costume "Unique" Helper

      function unique(array) {
        const newArray = [];
        return array.reduce(function(prev, element){
            if(!prev.includes(element)) {
                prev.push(element);
                return prev;
            }
        }, []);
      }

      var numbers = [1, 1, 2, 3, 4, 4];
      unique(numbers);

Coding Exercise 17: A Constant Exercise of Letting Variable be Variables

      const name = "Johnny";
      let age = 20;
      const dateOfBirth = '06/06/1997';

Coding Exercise 18: Const/Let Refactoring

      let statuses = [ 
        { code: 'OK', response: 'Request successful' },
        { code: 'FAILED', response: 'There was an error with your request' },
        { code: 'PENDING', response: 'Your reqeust is still pending' }
      ];
      let message = '';
      var currentCode = 'OK';

      for (let i = 0; i < statuses.length; i++) {
        if (statuses[i].code === currentCode) {
          message = statuses[i].response;
        }
      }

Coding Exercise 19: Template Strings in Practice

      function doubleMessage(number) {
        return `Your number doubled is ${2 * number}`;
      }
      
Coding Exercise 20: Name Helpers

      const fullName = (firstName, lastName) => `${firstName} ${lastName}`;

Coding Exercise 21: Refactoring Keywork Functions

      const fibonacci = n => {
        if (n < 3) return 1;
        return fibonacci(n - 1) + fibonacci(n - 2);
      };

Coding Exercise 22: Arrow Functions aren't always a solution

      const profile = {
          name: 'Alex',
          getName: function () {
              return this.name;
          }

      };

Coding Exercise 23: Multiple Properties With Enhanced Notation

      const red = '#ff0000';
      const blue = '#0000ff';

      const COLORS = { red, blue };

Coding Exercise 24: Condesing Code with Literal Enhanced Literals

      const fields = ['firstName', 'lastName', 'phoneNumber'];

      const props = { fields };

Coding Exercise 25: Literals in Function

      const canvasDimensions = (width, initialHeight) => {
        const height = initialHeight * 9 /16;
        return { 
          width, 
          height 
        };
      };

Coding Exercise 26: Refactor to Use Enhanced Literal Notation

const color = 'red';

      const Car = {
        color,
        drive() {
          return 'Vroom!';
        },
        getColor() {
          return this.color;
        }
      };

Coding Exercise 27: Using Default Arguments

      function sum(a = 0, b =0) {
        return a + b;
      }

Coding Exercise 28: Dumping Unused Code

      function addOffset(style = {}) {

        style.offset = '10px';

        return style;
      }

Coding Exercise 29: Many, Many Arguments

      function product(...rest) {
        return rest.reduce(function(acc, number) {
          return acc * number;
        }, 1);
      }

Coding Exercise 30: Spreadin' Arrays

      function join(array1, array2) {
        [...array1, ...array2];
      }

Coding Exercise 31: Mixing Rest and Spread

      function unshift(array, ...rest) {
        return [...rest, ...array];
      }

Coding Exercise 32: Destructuring in Practice

      const profile = {
        title: 'Engineer',
        department: 'Engineering'
      };

      function isEngineer({ title, department }) {
        return title === 'Engineer' && department === 'Engineering';
      }

Coding Exercise 33: Array Destructuring in Practice

      const classes = [
        [ 'Chemistry', '9AM', 'Mr. Darnick' ],
        [ 'Physics', '10:15AM', 'Mrs. Lithun'],
        [ 'Math', '11:30AM', 'Mrs. Vitalis' ]
      ];

      const classesAsObject = classes.map(function(course){
          const [subject, time, teacher] = course;
          return {subject, time, teacher};
      });

Coding Exercise 34: Recursion with Destructuring

      const numbers = [1, 2, 3];

      function double([number, ...rest]) {
          if (!number) {
              return rest;
          } else {
              return [number * 2, ...double(rest)];
          }
      }

Coding Exercise 35: Game Classes

      class Monster {
        constructor(options) {
            this.health = 100;
            this.name = options.name;
        }
      }

Coding Exercise 36: Subclassing Monsters

      class Monster {
        constructor(options) {
          this.health = 100;
          this.name = options.name;
        }
      }

      class Snake extends Monster {
        constructor(options) {
          super(options);
        }
        bite(snake) {
            return snake.health -= 10;
        }
      }
