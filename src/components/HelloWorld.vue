<template>
  <h1>Hello World </h1>
      <div className="cards">
     
        
        
        <div className="card-container">
         
          <div className="card-content">
           
            <h2 className="cardTitle">PSU Blue and White</h2>
            
            <p> "Blue and White is a Penn State Football Game day where the team is split into two teams blue and white" : "Blue and White game day"</p>
    
            <img src="https://nittanylionswire.usatoday.com/wp-content/uploads/sites/100/2023/04/USATSI_20469545.jpg?w=1000" alt="Card Image" />
            <div>
           
              <button className="details-button">Toggle Description</button>
            </div>
           
           <p className="description-hidden">Blue and White is a Penn State Football Game day where the team is split into two teams blue and white</p>
          </div>
        </div>
      </div>
    
  </template>
  
  <script>
  export default {
    name: 'HelloWorld',
    props: {
      msg: String
    },
    mounted() {
      document.querySelector('#btn').addEventListener('click', () => {
        const clone = document.querySelector('.card').cloneNode(true); // Clone the whole card
        document.body.appendChild(clone);
      });
      
      var numbers = ["1", "2", "3", "4", "5", "6", "7", "8", "9"];
      var letters = ["A", "B", "C", "D", "E", "F"];
      
      function randomColor() {
        var color = "";
        for (var i = 0; i < 3; i++) {
          var index = Math.floor(Math.random() * (numbers.length + letters.length));
          color += (index < numbers.length) ? numbers[index] : letters[index - numbers.length];
        }
        return color;
      }
      
      document.querySelector('#colorBtn').addEventListener('click', () => {
        const card = document.querySelector('.card');
        // Change background color
        card.style.backgroundColor = '#' + randomColor();
      });
      
      // HEADING CHANGER
      document.querySelector('#Headingbtn').addEventListener('click', () => {
        const title = document.querySelector('h2');
        title.innerText = "Super Pod 2 Realty";
      });
      
      // Card delete
      document.querySelector('#dltbtn').addEventListener('click', () => {
        const cards = document.querySelectorAll('.card');
        // Check if there are cards to delete
        if (cards.length > 1) {
          const lastCard = cards[cards.length - 1];
          lastCard.parentNode.removeChild(lastCard);
        }
      });
      
      var original = document.querySelector('#description').innerText;
      
      document.querySelector('#detailsBtn').addEventListener('click', () => {
        const description = document.querySelector('#description');
        // Toggle the visibility of the description
        if (description.innerText === 'none' || description.innerText === '') {
          description.innerText = original; // Show the description
        } else {
          description.innerText = ''; // Hide the description
        }
      });
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  .App {
    text-align: center;
  }
  
  .cards {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    
  }
  
  .card-container {
    background-color: #001e44;
    width: 20%;
    height: 50%;
    display: block;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    border-radius: 10px;
  }
  
  
  
  .card-content {
    text-align: center;
    color: white;
    display: block;
    flex-direction: column;
    aign-content: center;
    justify-content: center;
    
  }
  
  
  .card-content> img{
    width: 200px;
    max-width:80%;
    border-radius: 10px;
  }
  
  
  .card-content button{
    margin-top:40px;
    text-decoration: none;
    background-color: #ffff;
    color:#001e44 ;
    padding: 8px 12px;
    border-radius: 5px;
  }
  
  .card-content button:hover{ 
    background-color: #001e44;
    color: white;
  
  }
  
  .card-content button a{
     text-decoration: none;
  }
  
  
  
  @media (max-width: 800px) {
   .details-button {
      display: none;
    }
  }
  
  
  @media (max-width: 500px) {
    .card {
      max-width: 300px;
    }
  }
  
  </style>
  