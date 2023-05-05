# arsalan-11865-sec-b
Javascript timer clock


let hours = prompt("Enter hours");
let minutes = prompt("Enter minutes");
let seconds = prompt("Enter seconds");

function startTimer() {
  if (seconds > 0) {
    seconds--;
  } else {
    if (minutes > 0) {
      minutes--;
      seconds = 59;
    } else {
      if (hours > 0) {
        hours--;
        minutes = 59;
        seconds = 59;
      } else {
        clearInterval(interval);
        // Play sound here
      }
    }
  }

  let hourString = hours < 10 ? "0" + hours : hours;
  let minuteString = minutes < 10 ? "0" + minutes : minutes;
  let secondString = seconds < 10 ? "0" + seconds : seconds;

  document.getElementById("timer").innerHTML =
    hourString + ":" + minuteString + ":" + secondString;
}

let interval = setInterval(startTimer, 1000);
