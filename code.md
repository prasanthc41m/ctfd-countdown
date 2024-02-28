<!-- CTFd countdown start -->
<h5 class="text-center">
<p id="ctfd"></p>

<script>
// Set the date and time for both countdowns
// var countDownDate1 = new Date("Jan 01 2030, 10:00:00").getTime();
// var countDownDate2 = new Date("Jan 07 2030, 10:00:00").getTime();  
var countDownDate1 = new Date("{{ctf_start}}").getTime();
var countDownDate2 = new Date("{{ctf_end}}").getTime();

var currentCountdown = countDownDate1; // Start with first countdown
var countdownText = document.getElementById("ctfd");

function updateCountdown() {
  // Get today's date and time
  var now = new Date().getTime();

  // Find the distance between now and the current countdown date
  var distance = currentCountdown - now;

  // Time calculations for days, hours, minutes and seconds
  var days = Math.floor(distance / (1000 * 60 * 60 * 24));
  var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  var seconds = Math.floor((distance % (1000 * 60)) / 1000);

  // Output the result with additional text based on current countdown
  var countdownPrefix = (currentCountdown === countDownDate1) ? "CTF will start in " : "CTF will end in ";
  if (distance > 0) {
    // Display normal countdown if time is positive
    if (days > 0) {
      countdownText.textContent = countdownPrefix + `${days} days ${hours}h ${minutes}m ${seconds}s`;
    } else {
      countdownText.textContent = countdownPrefix + `${hours}h ${minutes}m ${seconds}s`;
    }
  } else {
    // Show message when countdown is negative
    countdownText.textContent = "Wait for the next announcement!";
    // Switch to the other countdown immediately after displaying the message
    currentCountdown = (currentCountdown === countDownDate1) ? countDownDate2 : countDownDate1;
  }
}

// Update the countdown every 1 second
var x = setInterval(updateCountdown, 1000);
</script>
<!-- CTFd countdown start -->
