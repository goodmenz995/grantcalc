<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grant Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }

        label {
            display: block;
            margin-bottom: 5px;
        }

        input {
            margin-bottom: 10px;
        }

        button {
            padding: 8px 12px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <h1>Grant Calculator</h1>

    <label for="projectCost">Project Cost:</label>
    <input type="number" id="projectCost" placeholder="Enter project cost" required>

    <label for="grantPercentage">Grant Percentage:</label>
    <input type="number" id="grantPercentage" placeholder="Enter grant percentage" required>

    <button onclick="calculateGrant()">Calculate Grant</button>

    <h2>Grant Amount:</h2>
    <p id="grantAmount"></p>

    <script>
        function calculateGrant() {
            var projectCost = parseFloat(document.getElementById('projectCost').value);
            var grantPercentage = parseFloat(document.getElementById('grantPercentage').value);

            if (isNaN(projectCost) || isNaN(grantPercentage)) {
                alert("Please enter valid numbers.");
                return;
            }

            var grantAmount = (grantPercentage / 100) * projectCost;

            document.getElementById('grantAmount').innerHTML = "Grant Amount: $" + grantAmount.toFixed(2);
        }
    </script>

</body>
</html>
