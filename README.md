<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulario de Recolección de Datos</title>
</head>
<body>
    <h1>Formulario de Recolección de Datos</h1>
    <form action="process_form.php" method="post">
        <label for="name">Nombre:</label>
        <input type="text" id="name" name="name" required><br><br>
        
        <label for="email">Correo electrónico:</label>
        <input type="email" id="email" name="email" required><br><br>
        
        <label for="message">Mensaje:</label><br>
        <textarea id="message" name="message" rows="4" cols="50" required></textarea><br><br>
        
        <input type="submit" value="Enviar">
    </form>
</body>
</html>

<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = $_POST['name'];
    $email = $_POST['email'];
    $message = $_POST['message'];

    // Guardar los datos en un archivo CSV
    $data = array($name, $email, $message);
    $file = fopen('data.csv', 'a');
    fputcsv($file, $data);
    fclose($file);

    // Redirigir de vuelta al formulario o a una página de confirmación
    header('Location: index.html');
    exit;
}
?>
