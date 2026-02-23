<!DOCTYPE html>
<html>
<head>
    <title>BMI Calculator with Categories</title>
    <style>
        body {
            font-family: Arial;
            text-align: center;
            margin-top: 50px;
        }

        input {
            padding: 8px;
            margin: 5px;
        }

        button {
            padding: 8px 15px;
            cursor: pointer;
        }

        #result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h1>BMI Calculator with Categories</h1>

    <p>Enter your weight (kg) and height (meters):</p>

    <input type="number" id="weight" placeholder="Weight (kg)">
    <br>

    <input type="number" id="height" placeholder="Height (m)">
    <br><br>

    <button onclick="calculateBMI()">Calculate</button>

    <p id="result"></p>

    <script>
        function calculateBMI() {
            let weight = parseFloat(document.getElementById("weight").value);
            let height = parseFloat(document.getElementById("height").value);

            if (!weight || !height) {
                document.getElementById("result").innerText = "Please enter valid values.";
                return;
            }

            let bmi = weight / (height * height);
            let category = "";

            if (bmi < 18.5) {
                category = "Underweight";
            } 
            else if (bmi < 25) {
                category = "Normal weight";
            } 
            else if (bmi < 30) {
                category = "Overweight";
            } 
            else {
                category = "Obese";
            }

            document.getElementById("result").innerText =
                "Your BMI is " + bmi.toFixed(2) + " (" + category + ")";
        }
    </script>

</body>
</html>
