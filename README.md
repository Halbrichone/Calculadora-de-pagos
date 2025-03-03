# Calculadora-de-pagos
para generar tu pago responde las preguntas
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Pagos</title>
    <script>
        function calcularPago() {
            let base = 1700;
            let descuento = 0;

            let esAsociado = document.getElementById("asociado").checked;
            let esEstudiante = document.getElementById("estudiante").checked;
            let organizaCongreso = document.getElementById("organizador").checked;
            let menor40 = document.getElementById("menor40").checked;
            let prontoPago = document.getElementById("prontoPago").checked;

            if (esAsociado) descuento += 0.5; 
            if (esEstudiante) descuento += 0.6;
            if (organizaCongreso) descuento += 0.5;
            if (menor40) descuento += 0.2;
            if (prontoPago) descuento += 0.2;

            let montoFinal = base * (1 - descuento);
            if (montoFinal < 0) montoFinal = 0;

            document.getElementById("resultado").innerText = "Monto a pagar: $" + montoFinal.toFixed(2);
        }
    </script>
</head>
<body>
    <h2>Calculadora de Pagos</h2>
    <form>
        <label><input type="checkbox" id="asociado"> Es asociado</label><br>
        <label><input type="checkbox" id="estudiante"> Es estudiante</label><br>
        <label><input type="checkbox" id="organizador"> Organiza congreso</label><br>
        <label><input type="checkbox" id="menor40"> Menor de 40 años</label><br>
        <label><input type="checkbox" id="prontoPago"> Fecha de pronto pago</label><br>
        <button type="button" onclick="calcularPago()">Calcular</button>
    </form>
    <h3 id="resultado">Monto a pagar: $1700.00</h3>
</body>
</html>
