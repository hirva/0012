# 0012
##Project Assignment
````
1. Write a program in JavaScript to get the prime factorization of a given (small) integer. You may use the Sieve of Eratosthenes method to generate a list of primes if you wish.

<!DOCTYPE html>
<html>
<head>
    <title></title>
	<meta charset="utf-8" />
    
</head>
<body>
    Enter number:<input type="number" name="n1" id="n1" placeholder="enter number"/>
    <input type="button" value="find" onclick="getValue()"/>
    <script>
        function getValue() {
            var num = document.getElementById("n1").value;
            
            var arr = new Array();
            arr = primeFactorization(num);
            function primeFactorization(num) {

                var root = Math.sqrt(num),
                result = arguments[1] || [],  //get unnamed paremeter from recursive calls
                x = 2;

                if (num % x) {//if not divisible by 2 
                    x = 3;//assign first odd
                    while ((num % x) && ((x = x + 2) < root)) { }//iterate odds
                }
                //if no factor found then num is prime
                x = (x <= root) ? x : num;
                result.push(x);//push latest prime factor

                //if num isn't prime factor make recursive call
               
                if (x === num) {
                    return  result;
                }
                else {
                    return primeFactorization(num / x, result);
                }

                
            }

            document.write(arr);
            
        }
        </script>
</body>
</html>

2. Write a program in JavaScript to implement the Rock Paper Scissors Lizard Spock game in JavaScript. It takes as input, the choices of Player 1 and Player 2. The program should calculate the winner based onthe modular arithmetic solution described.

<!DOCTYPE html>
<html>
<head>
    <title></title>
	<meta charset="utf-8" />
</head>
<body>
    Player 1:
    <input type="radio" name="choice1" id="choice1" value="0"/>Rock
    <input type="radio" name="choice1" id="choice1" value="1" />Spock
    <input type="radio" name="choice1" id="choice1" value="2"/>Paper
    <input type="radio" name="choice1" id="choice1" value="3"/>Lizard
    <input type="radio" name="choice1" id="choice1" value="4"/>Scissor
    <br />
    <br />
    <hr />
    Player 2:
    <input type="radio" name="choice2" id="choice2" value="0"/>Rock
    <input type="radio" name="choice2" id="choice2" value="1"/>Spock
    <input type="radio" name="choice2" id="choice2" value="2"/>Paper
    <input type="radio" name="choice2" id="choice2" value="3"/>Lizard
    <input type="radio" name="choice2" id="choice2" value="4"/>Scissor
    <input type="button" value="game" onclick="getCheckedRadio()" />
    <script>
       
            function getCheckedRadio() {
                var radioButtons1 = document.getElementsByName("choice1");
                var radioButtons2 = document.getElementsByName("choice2");
                for (var x = 0; x < radioButtons1.length; x++) {
                    if (radioButtons1[x].checked) {
                        var ch1 =parseInt(radioButtons1[x].value);
                        break;

                    }
                }
                for (var k = 0; k < radioButtons2.length; k++) {
                        if (radioButtons2[k].checked) {
                            var ch2 =parseInt(radioButtons2[k].value);
                            break;
                           
                        }
                }
                var j = ch2 - ch1;
                    var i = (Math.abs((ch2 - ch1)) % 5);
                    if (i === 1 || i === 2) {
                        alert("Player 2 is winner");
                    }
                    else if (i === 3 || i === 4) {
                        alert("Player 1 is winner");
                    }
                    else if (i === 0) {
                        alert("It's a DRAW");
                    }
                }
            
        

    </script>

</body>
</html>

````
