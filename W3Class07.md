const hours = [
  "6am",
  "7am",
  "8am",
  "9am",
  "10am",
  "11am",
  "12pm",
  "1pm",
  "2pm",
  "3pm",
  "4pm",
  "5pm",
  "6pm",
  "7pm",
];

function randomNumber(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

function Shops(
  location,
  minCust,
  maxCust,
  avgCookiesPerCust,
  customersPerHour,
  cookiesPerHour,
  totalCookieSold
) {
  this.location = location;
  this.minCust = minCust;
  this.maxCust = maxCust;
  this.avgCookiesPerCust = avgCookiesPerCust;
  this.customersPerHour = customersPerHour;
  this.cookiesPerHour = cookiesPerHour;
  this.totalCookieSold = totalCookieSold;
  function calculateSales() {
    for (let i = 0; i < hours.length; i++) {
      const hourCustomers = randomNumber(this.minCust, this.maxCust);
      this.customersPerHour.push(hourCustomers);
      const hourCookiesSold = math.floor(
        hourCustomers * this.avgCookiesPerCust
      );
      this.cookiesPerHour.push(hourCookiesSold);
      this.totalCookieSold = this.totalCookieSold + hourCookiesSold;
    }
  }

  this.calculateSales();
}

Shops.prototype.render = function () {
  const shopSales = document.getElementById("shopSales");

  const article = document.createElement("article");

  const h2 = document.createElement("h2");
  h2.textContent = shops.calculateSales;
  article.appendChild(h2);

  const p = document.createElement("p");
  p.textContent = `${shops.calculateSales} is ${shops.cookiesPerHour} avergeing ${shops.avgCookiesPerCust}`;
  article.appendChild(p);

  const salesData = document.getElementById("salesData");

  const ul = document.createElement("ul");
  for (let i = 0; i < Shops.calculateSales.length; i++) {
    const li = document.createElement("li");
    li.textContent = Shops.calculateSales[i];
    ul.appendChild(li);

    shopSales.appendChild(ul);
  }

  const seattle = new Shops("Seattle", 23, 65, 6.3, [], [], 0);

  const tokyo = new Shops("Seattle", 3, 24, 1.2, [], [], 0);

  const dubai = new Shops("Dubai", 11, 38, 3.7, [], [], 0);

  const paris = new Shops("Paris", 20, 38, 2.3, [], [], 0);

  const lima = new Shops("Lima", 2, 16, 4.6, [], [], 0);

  seattle.render();
  tokyo.render();
  dubai.render();
  paris.render();
  lima.render();
};

Class 07 - Object-Oriented Programming, HTML Tables
 

Domain modelingLinks to an external site.
Domain modeling is a way of conceptualising code before actually writing any which describes the different parts of the script along with their attributes and behaviours. This is important as it allows for technically minded and non-technically minded people to to discuss a problem and the eventual solution.

HTML tablesLinks to an external site.
In HTML tables shouldn’t be used for layouts because:

they reduce accessibility
the code required is hard to read
they are not naturally responsive
Three semantic table elements are:

th - table header
tr - table row
td - table data cell
ConstructorsLinks to an external site.
In JavaScript a constructor is a function that creates a new object , and is called using the new keyword. For instance:

    function Cat(name){
      this.name = name;
      this.meow = function (){
        alert(`My name is ${name}. Meow!`)
      }
    }

    const whisper = new Cat("Whisper");
With constructors the this keyword is bound to the new object so it can be used in the creation of the new object.

PrototypesLinks to an external site.
Prototype can be used to alter an existing object without redeclaring it, for instance:

    function Cat(name){
      this.name = name;
      this.meow = function (){
        alert(`My name is ${name}. Meow!`)
      }
    }

    Cat.prototype.family = "Felidae"
