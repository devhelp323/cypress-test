# The Flaky Test Challenge
# My solution
added "defaultCommandTimeout": 4500 into cypress.json because savePeople function(./src/api/client.js) is executed between 3500 and 4500

# cypress.json

{
  "baseUrl": "http://localhost:3000",
  "defaultCommandTimeout": 4500
}

# Because ./src/api/client.js

  savePeople: function(people) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        localStorage.people = JSON.stringify(people);
        return resolve({success: true});
      }, between(3500, 4500));
    });
  }
  

