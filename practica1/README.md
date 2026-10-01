## 1. Diseño y Requisitos

### Dominios elegidos

Para la infraestructura se ha elegido dos dominios ficticios uno para cada marca


- **Marca 1:** "HRjuandragontech.local"
- **Marca 2:** "HRshadowbyte.local"


Se han elegido estos nombre para diferenciar las 2 marcas que serian alojadas en la misma infraestructura. Ambos dominios son ficticios.


### 2. MPM de Apache elegido

El MPM elegido para Apache es **event**

Se ha escogido **event** porque permite gestionar de forma eficiente un gran número de conexiones sumultaneamente y aprovecha mejor los recursos<br>
 del sevidor. 

Su modelo de funcionamiento permite gestionar conexiones persistentes de manera eficiente.<br> 

Evitando mantener procesos inncesarios durante toda la conexion

### 3. Arquitectura inicial

En la primera fase se utilizara un servidor apache para alojar las 2 marcas mediante **Virtual Hosts**

Cada dominio tendra su propio Virtual Hosts y su propio directorio de documentos


Cliente
	|
	|--- HRjuandragontech.local
	|
	|___ HRshadowbyte.local
		    |
		    |
	     Servidor Apache
		    |
		    |
       --------------------------
       |                        |
   Hrjuandragontech         HRshadowbyte.local
