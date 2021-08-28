# Number-Guesser-Game
Codecademy Project is a number-guessing game.
The project is to create 4 JS functions to power the game. The code will run in the browser instead of just the terminal.
//Function (1 of 4) should return a secret, random integer between 0 and 9 at the start of each new round
// Function (2 of 4), determines which player wins based on which guess is closer, human wins if tied, returns true if human wins and false if computer wins.
// Function (3 of 4) Parameter will be a string value representing the winner, increases the score variable (humanScore or computerScore) by 1 depending on winner passed in to updateScore, string passed in will be either 'human' or 'computer', does not need to return any value.
// Function (4 of 4) should increase value of currentRoundNumber by 1
let humanScore = 0;
let computerScore = 0;
let currentRoundNumber = 1;

//Function (1 of 4) should return a secret, random integer between 0 and 9 at the start of each new round
const generateTarget = () => {
    let x = Math.floor(Math.random()*10);
    return x;
  };  
  
// Function (2 of 4), determines which player wins based on which guess is closer, human wins if tied, returns true if human wins and false if computer wins.
const compareGuesses = (userGuess, computerGuess, target) => {
      if (userGuess === computerGuess || userGuess === target) {
          return true;
      } else if (computerGuess === target) {
          return false;
      }
      let ansOne = Math.abs(target - userGuess);
      let ansTwo = Math.abs(target - computerGuess);
      if (ansOne === ansTwo || ansOne < ansTwo) {
          return true;
      } else {
          return false;
      }
  };
  
// Function (3 of 4) Parameter will be a string value representing the winner, increases the score variable (humanScore or computerScore) by 1 depending on winner passed in to updateScore, string passed in will be either 'human' or 'computer', does not need to return any value.
const updateScore = winner => {
    if (winner === 'human') {
        humanScore++;
    } else {
        computerScore++;
    }
};
  
// Function (4 of 4) should increase value of currentRoundNumber by 1
const advanceRound = () => {
    currentRoundNumber++;
};  
