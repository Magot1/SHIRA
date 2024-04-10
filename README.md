<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Perfil de Usuario</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="profile">
        <img src="profile_picture.jpg" alt="Foto de Perfil">
        <h1>Nombre de Usuario</h1>
        <p>Descripción del perfil...</p>
        <ul>
            <li><strong>Publicaciones:</strong> 100</li>
            <li><strong>Seguidores:</strong> 1000</li>
            <li><strong>Siguiendo:</strong> 500</li>
        </ul>
    </div>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f0f0f0;
}

.profile {
    max-width: 600px;
    margin: 50px auto;
    padding: 20px;
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    text-align: center;
}

.profile img {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    margin-bottom: 20px;
}

.profile h1 {
    font-size: 24px;
    margin-bottom: 10px;
}

.profile p {
    font-size: 16px;
    color: #888;
    margin-bottom: 20px;
}

.profile ul {
    list-style-type: none;
    padding: 0;
}

.profile ul li {
    font-size: 16px;
    margin-bottom: 10px;
}

.profile ul li strong {
    font-weight: bold;
    margin-right: 5px;
}
