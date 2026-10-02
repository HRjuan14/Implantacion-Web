# 1. Diseño y requisitos

## Dominios elegidos

Para hacer la práctica se han elegido dos dominios ficticios, uno para cada marca:

* **Marca 1:** `HRjuandragontech.local`
* **Marca 2:** `HRshadowbyte.local`

Los dos dominios son inventados y se utilizarán para diferenciar las dos marcas, aunque ambas estarán alojadas en el mismo servidor.

## 2. MPM de Apache elegido

El MPM que se va a utilizar en Apache es **event**.

He elegido este MPM porque está pensado para trabajar con bastantes conexiones al mismo tiempo y permite aprovechar mejor los recursos del servidor. También funciona bien con conexiones persistentes, ya que no es necesario mantener un proceso ocupado mientras la conexión está esperando.

Por este motivo, `event` resulta adecuado para el servidor que se plantea en esta práctica.

## 3. Arquitectura inicial

En la primera fase se utilizará un único servidor Apache para alojar las dos marcas. Para separarlas se utilizarán **Virtual Hosts**.

Cada dominio tendrá su propio Virtual Host y también tendrá un directorio independiente donde estarán sus archivos.

La estructura inicial sería la siguiente:

```text
Cliente
   |
   |--- HRjuandragontech.local
   |
   |--- HRshadowbyte.local
            |
            |
      Servidor Apache
            |
     -------------------
     |                 |
     |                 |
HRjuandragontech   HRshadowbyte
```

De esta forma, las dos marcas estarán en el mismo servidor, pero cada una tendrá su propia configuración y sus propios archivos.
