En esta version, el mapa se genero, falta probar que el mapa se genere con el movimiento del robot, tenemos las publicaciones de los frames /odom /map y las de urdf que contienen a /laser

**Cosas que instalar**

- `sudo apt-get install ros-humble-navigation2 ros-humble-nav2-bringup`, para el SLAM
- `sudo apt-get install ros-humble-slam-toolbox`, para el SLAM
- `sudo apt-get install ros-humble-xacro`
- `sudo apt-get install ros-humble-robot-localization`
- `sudo apt-get install ros-humble-joy`
- `sudo apt-get install ros-humble-joy-teleop`
- `sudo apt-get install ros-humble-tf-transformations`
- [Paquete del rplidar](https://github.com/babakhani/rplidar_ros2)



**Comandos a Ejecutar**

---- **Comandos que reemplazan a ROS2CONTROL** ----

- `ros2 launch robix_controller joystick_teleop.launch` para iniciar conexión con el joystick.
- `ros2 run robix_firmware simple_serial_transmitter` para enviar comandos de `/cmd_vel` a Arduino.
- `ros2 run robix_firmware velocidad_ruedas_publisher` para enviar datos de encoder desde Arduino hasta Raspberry.
- `ros2 run robix_firmware odometry_publisher` para publicar los datos de odometría.
- `ros2 run robix_firmware tf_transmitter` para generar la publicación de las transformadas desde odometría a map.

---- **Iniciar cuerpo del robot** ----

- `ros2 launch robix_description display.launch` inicia todas las transformadas.

---- **Iniciar el Rplidar** ----

- `ros2 launch rplidar_ros2 rplidar.launch`

  Si todo está bien con `ros2 topic`, debería visualizar los tópicos `/TF`, `/ODOM` y `/SCAN`.

---- **Iniciar el SLAM** ---- 
(Tutorial: [Generar un mapa con slam_toolbox](https://roboticsbackend.com/ros2-nav2-generate-a-map-with-slam_toolbox/))

- `ros2 launch nav2_bringup navigation_launch.py`

ros2 launch slam_toolbox online_async_launch.py
rviz2 rviz2 (Hablitar TF, MAP,ODOMETRY) y selecionar fixed_frame "map"




