# Ejercicio 3 - SWARM (2 puntos)

Cree una página web básica (archivo HTML) en la cual se muestren los vínculos a dos archivos distintos alojados en Swarm además de su nombre.

En la subida de los archivos debe utilizar el cifrado disponible en Swarm.

No se considerará válido si se suben los contenidos por separado y se vinculan en el archivo HTML posteriormente. Al navegar entre los archivos, el hash de Swarm mostrado en la barra de direcciones no debe cambiar.

La respuesta a este ejercicio debe ser algo de este estilo:

![./images/Screenshot_0.jpg](./images/Screenshot_0.jpg)

No es necesario vincular el hash de Swarm a ENS.

---
**1º)** Preparamos Swarm de acuerdo a lo indicado en la web https://swarm-guide.readthedocs.io/en/latest/installation.html.  

Dado que el repositorio PPA ya quedó preparado con la instalación de Ethereum, solo ejecutamos:

> _$ sudo apt-get update_  
> _$ sudo apt-get install ethereum-swarm_

![./images/Screenshot_1.jpg](./images/Screenshot_1.jpg)

Comprobamos se ha instalado correctamente:

![./images/Screenshot_2.jpg](./images/Screenshot_2.jpg)

**2º)** Continuamos con las indicaciones según la web https://swarm-guide.readthedocs.io/en/latest/gettingstarted.html

- Creamos una cuenta con Geth:

> _$ geth account new_

![./images/Screenshot_3.jpg](./images/Screenshot_3.jpg)

> _b5d33f3957b8b923ac82db1ded35ee4e0238c49e_

- Conectamos con Swarm utilizando la nueva cuenta

> _$ swarm --bzzaccount b5d33f3957b8b923ac82db1ded35ee4e0238c49e_

![./images/Screenshot_4.jpg](./images/Screenshot_4.jpg)

- Verificamos que nuestro nodo local está funcionando:

> _http://localhost:8500_

![./images/Screenshot_5.jpg](./images/Screenshot_5.jpg)

**3º)** Abrimos otro terminal para subir los componentes de la web:

>Los componentes a subir están en el directorio [web](./web/) y son:
- _index.html_
- _documento1.txt_
- _documento2.txt_

> El comando para ello es:  
> _$ swarm --defaultpath index.html --recursive up --encrypt web_

Con _defaultpath_ se mostrará por defecto el fichero indicado (cuando se utilice la url de Swarm), con _recursive_ se subirán los ficheros y carpetas incluidos en el directorio indicado y con _encrypt_ el contenido subirá encriptado y el resto de usuarios no lo podrá utilizar.

![./images/Screenshot_6.jpg](./images/Screenshot_6.jpg)

Obtenemos el hash:
_de9c4451590b4ebba7ddfc539596ed5542f8f78ed6b7ce8dda3db4dd1f3a841a1c163750e4e9c5cf755cceeff2bc2a0c1ffef56a167aa5b00381ce9a84df7ecd_

**4º)** Con este hash componemos la url en Swarm y comprobamos que los componentes se han cargado correctamente:

[http://localhost:8500/bzz:/de9c4451590b4ebba7ddfc539596ed5542f8f78ed6b7ce8dda3db4dd1f3a841a1c163750e4e9c5cf755cceeff2bc2a0c1ffef56a167aa5b00381ce9a84df7ecd](http://localhost:8500/bzz:/de9c4451590b4ebba7ddfc539596ed5542f8f78ed6b7ce8dda3db4dd1f3a841a1c163750e4e9c5cf755cceeff2bc2a0c1ffef56a167aa5b00381ce9a84df7ecd)

![./images/Screenshot_7.jpg](./images/Screenshot_7.jpg)

> Podemos comprobar que al pinchar sobre ambos documentos el hash en la barra del explorador no cambia:
- documento1.txt  
![./images/Screenshot_8.jpg](./images/Screenshot_8.jpg)
- documento2.txt  
![./images/Screenshot_9.jpg](./images/Screenshot_9.jpg)







