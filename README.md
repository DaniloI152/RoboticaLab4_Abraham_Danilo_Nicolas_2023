## Laboratorio 4 Robótica
### Integrantes: 
- Danilo Enrique Insuasty Delgado.
- Abraham Másmela Ramirez.
- Nicolás Prieto Solano.


## Objetivos:
• Crear todos los Joint Controllers con ROS para manipular servomotores Dynamixel AX-12 del robot Phantom X Pincher. <br>
• Manipular los tópicos de estado y comando para todos los Joint Controllers del robot Phantom X Pincher. <br>
• Manipular los servicios para todos los Joint Controllers del robot Phantom X Pincher. <br>
• Conectar el robot Phantom X Pincher con MATLAB o Python usando ROS. <br>


## Parametros DH del robot Pincher
El diagrama que describe el robot pincher es el siguiente

<div>
<p style = 'text-align:center;' align="center">
<img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/robot%20general.png" width="500px" >
</p>
</div>
Los marcos de referencias para describir el robot a traves de los parametros DH con base en el diagrama del robot pincher y las distancias de las articulaciones ya medidas son:

<div>
<p style = 'text-align:center;' align="center">
<img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/robot%20general%20dh.png" width="500px" >
</p>
</div>
La tabla con los parametros DH se muestra a continuación

<div>
<p style = 'text-align:center;' align="center">
<img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/parametros%20DH.PNG" width="500px" >
</p>
</div>

Con los parametros DH se pueden contruir las matrices que describen cada eslabon respecto al otro. Las siguientes son las matrices de cada eslabon

<div>
<p style = 'text-align:center;' align="center">
<img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/Matrices%20DH.PNG" width="200px" >
</p>
</div>

La matriz de la herramienta es la siguiente. La distancia medida entre el centro del griper y es eslabon es de 1cm.

<div>
<p style = 'text-align:center;' align="center">
<img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/matriz%20tcp.PNG" width="200px" >
</p>
</div>


la matriz de transformación homogénea desde la base hasta el efector final que es la multiplicacion consecutiva de las matrices mostradas anteriormente es:


<div>
<p style = 'text-align:center;' align="center">
<img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/matriz%20base%20efector%20final.PNG" width="800px" >
</p>
</div>

donde:

<div>
<p style = 'text-align:center;' align="center">
<img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/variables%20matriz%20base%20tcp.PNG" width="300px" >
</p>
</div>



## Desarrollo:
Se realizan las siguientes poses generadas a partir de los valores articulares de q1, q2, q3, q4, q5. <br>
| Pose | Valores articulares |
|------|---------------------|
| 1   | 0, 0, 0, 0, 0.       |
| 2   | -25, 15, -20, 20, 0 |
| 3   | 35, -35, 30, -30, 0 |
| 4   | -85, 20, -55, 17, 0|
| 5   | -80, 35, -55, 45, 0|

A continuación se muestran las posiciones, teniendo en cuenta que nuestro **Home** fue tomado con los valores articulares de 0, 0, 0, 0, 0,  :<br>
• Posiciones del robot:
<div>
  <p style = 'text-align:center;' align="center">
    <img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/PosHome.gif" width="180px">
    <img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/Pos2.gif" width="180px">
    <img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/Pos3.gif" width="180px">
    <img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/Pos4.gif" width="180px">
    <img src="https://github.com/DaniloI152/RoboticaLab4_Abraham_Danilo_Nicolas_2023/blob/main/Imagenes/Pos5.gif" width="180px">
  </p>
  <p style = 'text-align:center;' align="center">
    Posición 1-Home, 2, 3, 4 y 5.
  </p>
</div>
A continuación se muestra el video donde el robot alcanza cada una de las posiciones que son seleccionadas por el usuario:
<a href="https://www.youtube.com/watch?v=clO8sN_ds0M" target='blank'><img width=500px src="Videos/Miniatura1.png"/></a>
