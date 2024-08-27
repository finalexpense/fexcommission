# fexcommission
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Insurance Commission Calculator</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        label, input, button { display: block; margin: 10px 0; }
        button { padding: 5px 10px; }
        h2 { margin-top: 20px; }
    </style>
</head>
<body>
    <h1>Insurance Commission Calculator</h1>
    
    <label for="company">Insurance Company:</label>
    <select id="company">
        <option value="American Amicable">American Amicable</option>
        <option value="Royal Neighbors">Royal Neighbors</option>
        <!-- Add more options as needed -->
    </select>
    
    <label for="product">Product Type:</label>
    <select id="product">
        <option value="Level/AA/0-79">Level/AA/0-79</option>
        <option value="Graded/AA/80-85">Graded/AA/80-85</option>
        <option value="Level/RN/50-75">Level/RN/50-75</option>
        <!-- Add more options as needed -->
    </select>
    
    <label for="premium">Policy Premium:</label>
    <input type="number" id="premium" step="0.01" value="70">
    
    <label for="commissionLevel">Commission Level (%):</label>
    <input type="number" id="commissionLevel" step="0.01" value="50" min="10" max="100">
    
    <button onclick="calculate()">Calculate Commission</button>
    
    <h2>Results:</h2>
    <p id="result"></p>
    
    <script>
        function calculate() {
            const premium = parseFloat(document.getElementById('premium').value);
            const commissionLevel = parseFloat(document.getElementById('commissionLevel').value) / 100;

            const commission = premium * commissionLevel;
            
            document.getElementById('result').innerHTML =
                `Policy Premium: $${premium.toFixed(2)}<br>` +
                `Commission Level: ${commissionLevel * 100}%<br>` +
                `Commission: $${commission.toFixed(2)}`;
        }
    </script>
</body>
</html>
