<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Converter</title>
    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #eef2f7;
            font-family: Arial, sans-serif;
        }

        .calculator {
            width: min(92vw, 400px);
            padding: 20px;
            border-radius: 16px;
            background: #1f2937;
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
        }

        h1 {
            margin: 0 0 16px;
            color: white;
            font-size: 24px;
            text-align: center;
        }

        .display {
            min-height: 150px;
            margin-bottom: 16px;
            padding: 14px 16px;
            border-radius: 10px;
            background: #111827;
            color: white;
            text-align: right;
            overflow-wrap: anywhere;
        }

        #message {
            min-height: 24px;
            color: #9ca3af;
            font-size: 15px;
        }

        .temperature {
            margin-top: 10px;
            color: #f9fafb;
            font-size: 19px;
            line-height: 1.7;
        }

        .input-label {
            display: block;
            margin-bottom: 8px;
            color: #d1d5db;
            font-size: 15px;
        }

        input {
            width: 100%;
            min-height: 52px;
            margin-bottom: 12px;
            padding: 10px 14px;
            border: 2px solid #4b5563;
            border-radius: 9px;
            background: #f9fafb;
            color: #111827;
            font-size: 20px;
            text-align: right;
        }

        input:focus,
        select:focus {
            border-color: #3b82f6;
            outline: none;
        }

        select {
            width: 100%;
            min-height: 52px;
            margin-bottom: 12px;
            padding: 10px 14px;
            border: 2px solid #4b5563;
            border-radius: 9px;
            background: #f9fafb;
            color: #111827;
            font-size: 17px;
        }

        .buttons {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
        }

        button {
            min-height: 52px;
            border: 0;
            border-radius: 9px;
            background: #374151;
            color: white;
            cursor: pointer;
            font-size: 17px;
            transition: background 0.15s, transform 0.15s;
        }

        button:hover {
            background: #4b5563;
        }

        button:active {
            transform: scale(0.96);
        }

        .calculate {
            background: #059669;
        }

        .calculate:hover {
            background: #10b981;
        }

        .clear {
            background: #dc2626;
        }

        .clear:hover {
            background: #ef4444;
        }
    </style>
</head>
<body>
    <main class="calculator" aria-label="Temperature converter">
        <h1>Temperature Converter</h1>

        <section class="display" aria-live="polite">
            <div id="message">Enter a temperature value</div>
            <div id="output" class="temperature">
                <div>Celsius: —</div>
                <div>Fahrenheit: —</div>
                <div>Kelvin: —</div>
            </div>
        </section>

        <form id="temperatureForm">
            <label class="input-label" for="temperature">Temperature value</label>
            <input id="temperature" name="temperature" type="number" step="any" placeholder="Enter a value" required>

            <label class="input-label" for="unit">Value type</label>
            <select id="unit" name="unit">
                <option value="celsius">Celsius (°C)</option>
                <option value="fahrenheit">Fahrenheit (°F)</option>
                <option value="kelvin">Kelvin (K)</option>
            </select>

            <div class="buttons">
                <button class="calculate" type="submit">Convert</button>
                <button class="clear" type="button" onclick="clearConverter()">Clear</button>
            </div>
        </form>
    </main>

    <script>
        var form = document.getElementById('temperatureForm');
        var temperatureInput = document.getElementById('temperature');
        var unitInput = document.getElementById('unit');
        var message = document.getElementById('message');
        var output = document.getElementById('output');

        form.addEventListener('submit', function (event) {
            event.preventDefault();

            var value = Number(temperatureInput.value);
            if (temperatureInput.value.trim() === '' || !Number.isFinite(value)) {
                message.textContent = 'Error';
                output.innerHTML = '<div>Please enter a valid number.</div>';
                return;
            }

            var celsius;
            if (unitInput.value === 'fahrenheit') {
                celsius = (value - 32) * 5 / 9;
            } else if (unitInput.value === 'kelvin') {
                celsius = value - 273.15;
            } else {
                celsius = value;
            }

            var fahrenheit = celsius * 9 / 5 + 32;
            var kelvin = celsius + 273.15;

            message.textContent = 'Conversion result';
            output.innerHTML =
                '<div>Celsius: ' + formatTemperature(celsius) + ' °C</div>' +
                '<div>Fahrenheit: ' + formatTemperature(fahrenheit) + ' °F</div>' +
                '<div>Kelvin: ' + formatTemperature(kelvin) + ' K</div>';
        });

        function formatTemperature(value) {
            return Number(value.toFixed(2));
        }

        function clearConverter() {
            temperatureInput.value = '';
            unitInput.value = 'celsius';
            message.textContent = 'Enter a temperature value';
            output.innerHTML =
                '<div>Celsius: —</div>' +
                '<div>Fahrenheit: —</div>' +
                '<div>Kelvin: —</div>';
            temperatureInput.focus();
        }
    </script>
</body>
</html>
