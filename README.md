# python
Proyectos en python
*********************
*	speedtestv1.py	*
*********************
- Modulos necesarios
speedtest-cli
python-telegram-bot
mysql-connector 

- Cometido
El cometido de este script es realizar un test de velocidad de linea y sacar cierta informacion. A continuacion con esa informacion realiza lo siguiente:
-> Si la velocidad de descarga o subida es inferior a x valor (deberemos modificar el codigo para indicarle los valores) realizara dos acciones:
	* Por un lado almacena la informacion en una base de datos mysql.
	* Por otro lado realiza la notificacion por medio de un bot de telegram indicando que hay un problema en la velocidad.
-> Si la velocidad de descarga o subida es superior al valor fijado, guardara la informacion en la base de datos mysql, pero no nos notificara por el bot de telegram.
