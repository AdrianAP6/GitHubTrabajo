# GitHubTrabajo
***************Abre
* PHP script, ASCII text, with CRLF line terminators
<?php

$conexion = new mysqli("localhost", "root", "","contactos");
    if($conexion){
        echo "La gestion fue exitosa !!";
        header("Location: index.php");
    }else{
    echo "Fallo la gestion";
    }
?>
**************estilo
* ASCII text, with CRLF line terminators
*{
    margin: 0; padding: 0;
}

input:focus {
    background-color:darkgoldenrod;
}

html{
    width: 750px; height: 750px;
    background-color: black;
}

body{
    width: 375px; height: 375px;
    margin: auto; background-color: burlywood;
    padding: 30px;
}
**************guardar
* PHP script, ASCII text, with CRLF line terminators
<?php

include("abre.php");

$Nombre     = $_POST['Nombre'];
$Apellidos  = $_POST['Apellidos'];
$Calle      = $_POST['Calle'];

$consulta = "INSERT INTO clientes(Nombre, Apellidos, Calle) VALUES
('$Nombre', '$Apellidos', '$Calle')";

    if ($conexion->query($consulta) --- TRUE){
        header("Location: index.php");/**/
    }else{
        echo "Error: * . $consulta ."<br>" . $conexion->error;
    }
    $conexion->close();

?>
************index
* HTML document, ASCII text, with CRLF line terminators
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title>Formulario de Contacto</title>
<Link href="estilo.css" rel="stylesheet" />
    </head>
    <body>

        <h2>Formulario de Contacto</h2>

        <form class="clientes" action="guardar.php" method="POST" id="contact_form" runat="server" enctype="multipart/form-data">

            <label for="Nombre">Nombre:</label><br>
            <input type="text" id="Nombre" name="Nombre" maxlength="30"required ><br>

            <label for="Apellidos">Apellidos:</label><br>
            <input type="text" id="Apellidos" name="Apellidos" maxlength="60"required ><br><br>

            <label for="Calle">Calle:</label><br>
            <input type="text" id="Calle" name="Calle" maxlength="60"required ><br><br>


            <button class="submit" type="submit">Enviar Registro</button>
            </form>
    </body>
</html>
