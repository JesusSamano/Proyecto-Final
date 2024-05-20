
# Compra de Automóviles de Lujo

## Introducción
Nuestro proyecto consiste en una aplicación web para comprar automóviles de lujo. Nuestros usuarios pueden ver los diferentes autos que están disponibles. 
La ventaja es que al utilizar nuestra web podrás tener la oportunidad de visualizar ofertas y saber cuál es el auto con el menor precio, así optimiza sus finanzas.

## Estructura del Proyecto

### Página
- **Index.html**  
  [![Código](https://img.shields.io/badge/-Ver%20Código-blue)](###Códigos/###Index.html)

- **Db.php**  
  [![Código](https://img.shields.io/badge/-Ver%20Código-blue)](#db-php)

- **Validar.php**  
  [![Código](https://img.shields.io/badge/-Ver%20Código-blue)](#validar-php)

- **Home2.php**  
  [![Código](https://img.shields.io/badge/-Ver%20Código-blue)](#validar-php)


## CAPTURAS DE PANTALLA
Muestra de la interfaz al usuario.
### LOGGIN
<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/090a3313-e36b-430a-a4c8-3d1181597930" alt="Captura de Pantalla 1" width="400"/></td>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/cbbd648e-eb1b-409f-ae4c-95cf9151c09e" alt="Captura de Pantalla 2" width="400"/></td>
  </tr>
</table>

### Home
Esta es la parte que el usuario visualiza despues del el loggin
<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/80fc9a0d-f9ce-4cea-a031-f598e067084a" alt="Captura de Pantalla 1" width="900"/></td>
      </tr>
</table>

### Función
Nuestra web funciona a través de boots, estos boots bajan o suben los precios de los autos, y otro boot te avisa cual es auto con más económico.

En la imagen de lado izquierdo se visualiza una ventana con los unos precios, la otra imagen del lado derecho los precios han bajado y una alerta del carro más económico  

<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/80fc9a0d-f9ce-4cea-a031-f598e067084a" width="600"/></td>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/9dbaded6-eaaf-4970-a975-51feb6f9c250" width="600"/></td>  
 </tr>
</table>

![image](https://github.com/JesusSamano/Proyecto-Final/assets/113057832/c816f3db-657c-4736-92b8-a180a6b0d4da)

Esto ayuda bastante a los clientes que tienen un presupuesto y ayuda a quién vende el auto para que este sea adquirido más rápido, con nosotros en ganar ganar. 


---

## Códigos

### Index.html
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>login</title>
    <link rel="stylesheet" href="css/login.css">
```


### Db.php
```
<?php
$conexion=mysqli_connect("*******","*******","*******","*******")or die("error de conexion");
?>
```

### Validar.php
```
<?php
include('db.php');
$usuario=$_POST['usuario'];
$password=$_POST['password'];


$consulta="SELECT*FROM usuarios where usuario='$usuario' and password='$password'";
$resultado=mysqli_query($conexion,$consulta);

$filas=mysqli_num_rows($resultado);

if($filas){
  
    header("location:home2.php");

}else{
    ?>
    <?php
    include("index.html");

  ?>
  <h1 class="bad">ERROR DE AUTENTIFICACION</h1>
  <?php
}
mysqli_free_result($resultado);
mysqli_close($conexion);
```

### Home2.php
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta
            name="viewport"
            content="width=device-width, initial-scale=1.0"
        />
        <title>Carrillo</title>
        <link rel="stylesheet" href="styles.css" />

    </head>....(En esta version no se le muestra todo el codigo, para más información consulte la documentación)
```

## Base de datos

### Creacion de base de datos
```
CREATE TABLE `usuarios` (
  `ID` int(11) NOT NULL,
  `usuario` varchar(50) NOT NULL,
  `password` varchar(50) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```

### Registro de usuarios
```
INSERT INTO `usuarios` (`ID`, `usuario`, `password`) VALUES
(1, 'Luis', 'Luisjuan'),
(2, 'Juan', 'Juanje');
```

<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/195572b0-02f3-4b21-b128-307c5e231a8a" width="400"/></td>
 </tr>
</table>

## Conexion de base de datos con docker
Iniciamos la instalación de mysql- server
<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/9e1760b8-5ca5-47a2-a0a8-06362cbd33b1" width="400"/></td>
 </tr>
</table>
Creamos un contenedor mediante comandos
<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/ada7ae84-8c37-4174-9649-86a505083f31" width="400"/></td>
 </tr>
</table>

## Funcionando en Docker 
<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/2993491f-3483-42bb-852e-3377f08ea7fe" width="400"/></td>
 </tr>
</table>

### Contenedor 

<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/f47fda93-cd49-4b7b-84fc-22f0f10cb546" width="400"/></td>
 </tr>
</table>
--- 

## Orquestar base de datos con Kubernetes. 
Instalamos operadores para utilizar comandos.

<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/eb0457b2-01f6-44d8-bd72-f9825878332c" width="400"/></td>
 </tr>
</table>

Procedemos con la configuración
<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/752bc593-8180-446d-b6b8-9e6b63969556" width="200"/></td>
 </tr>
</table>

Levantamos el cluster.
<table>
  <tr>
    <td><img src="https://github.com/JesusSamano/Proyecto-Final/assets/113057832/d6a364c7-abaa-4841-a932-a55181b46e1c" width="400"/></td>
 </tr>
</table>



