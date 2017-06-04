---
title: "Tipos de mapas de bits | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - ".bmp (archivos)"
  - ".gif (archivos)"
  - ".jpeg (archivos)"
  - "mapas de bits [Windows Forms], formato de archivo"
  - "archivo de imagen intercambiable (EXIF)"
  - "formato de archivo EXIF"
  - "gif (archivos)"
  - "gráficos [formularios Windows Forms], formatos de archivo"
  - "Formato de intercambio de gráficos"
  - "imágenes [Windows Forms], formatos de archivo"
  - "JPEG (Joint Photographic Experts Group)"
  - "jpeg (archivos)"
  - "imágenes, formatos de archivo"
  - "PNG (archivos)"
  - "Formato PNG (Portable Network Graphics)"
  - "Formato TIFF"
  - "TIFF (archivos)"
ms.assetid: 6be085a2-2c13-47c8-b80a-c18b32777d8d
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Tipos de mapas de bits
Un mapa de bits es una matriz de bits que especifica el color de cada píxel de una matriz rectangular de píxeles.  El número de bits asignado a un píxel individual determina el número de colores que se pueden asignar a dicho píxel.  Por ejemplo, si cada píxel se representa con 4 bits, a un píxel determinado se le podrá asignar uno entre los 16 colores distintos \(2^4 \= 16\).  En la siguiente tabla se muestran unos cuantos ejemplos del número de colores que se le pueden asignar a un píxel que se representa con un número de bits determinado.  
  
|Bits por píxel|Número de colores que se le pueden asignar a un píxel|  
|--------------------|-----------------------------------------------------------|  
|1|2^1 \= 2|  
|2|2^2 \= 4|  
|4|2^4 \= 16|  
|8|2^8 \= 256|  
|16|2^16 \= 65,536|  
|24|2^24 \= 16,777,216|  
  
 Los archivos de disco que almacenan mapas de bits contienen, por lo general, uno o varios bloques de información que almacenan datos como, por ejemplo, el número de bits por píxel, número de píxeles de cada fila y número de filas de la matriz.  Un archivo de este tipo podría contener también una tabla de colores \(a veces se denomina paleta de colores\).  Una tabla de colores asigna números a colores específicos en el mapa de bits.  En la siguiente ilustración se muestra una imagen ampliada junto con el mapa de bits y la tabla de colores correspondientes.  Cada píxel se representa con un número de 4 bits y, por lo tanto, hay 2^4 \= 16 colores en la tabla de colores.  Cada color de la tabla se representa con un número de 24 bits: 8 bits para el rojo, 8 bits para el verde y 8 bits para el azul.  Los números se muestran en formato hexadecimal \(base 16\): A \= 10, B \= 11, C \= 12, D \= 13, E \= 14, F \= 15.  
  
 ![Ejemplo de mapa de bits](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art01.png "AboutGdip03\_Art01")  
  
 Observe el píxel de la fila 3, columna 5 de la imagen.  El número correspondiente en el mapa de bits es 1.  La tabla de colores indica que el 1 representa el color rojo y, por ello, el píxel es rojo.  Todas las entradas de la fila superior del mapa de bits son el número 3.  La tabla de colores indica que el 3 representa el azul, así que todos los píxeles de la fila superior de la imagen son azules.  
  
> [!NOTE]
>  Algunos mapas de bits se almacenan en formato ascendente; los números de la primera fila del mapa de bits se corresponden con los píxeles de la fila inferior de la imagen.  
  
 Un mapa de bits que almacena índices en una tabla de colores se denomina mapa de bits de paleta indizada.  Algunos mapas de bits no necesitan una tabla de colores.  Por ejemplo, si un mapa de bits utiliza 24 bits por píxel, el propio mapa de bits puede almacenar los colores en lugar de los índices de una tabla de colores.  En la siguiente ilustración se muestra un mapa de bits que almacena colores directamente \(24 bits por píxel\) en lugar de utilizar una tabla de colores.  En la ilustración se muestra también una vista ampliada de la imagen correspondiente.  En el mapa de bits, FFFFFF representa el blanco, FF0000 representa el rojo, 00FF00 representa el verde y 0000FF representa el azul.  
  
 ![Ejemplo de mapa de bits](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art02.png "AboutGdip03\_Art02")  
  
## Formatos de archivos de gráficos  
 Hay muchos formatos estándar para guardar mapas de bits en archivos de disco.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] admite los formatos de archivos gráficos que se describen en los siguientes párrafos.  
  
### BMP  
 BMP es un formato estándar que Windows utiliza para almacenar imágenes independientes del dispositivo e independientes de la aplicación.  El número de bits por píxel \(1, 4, 8, 15, 24, 32 o 64\) de un archivo BMP determinado se especifica en un encabezado de archivo.  Los archivos BMP con 24 bits por píxel son muy comunes.  Los archivos BMP no suelen comprimirse y, por tanto, no son muy apropiados para su transferencia a través de Internet.  
  
### GIF \(Graphics Interchange Format, formato de intercambio de gráficos\)  
 GIF es un formato común de las imágenes que aparecen en páginas Web.  Los archivos GIF funcionan bien para dibujar líneas, imágenes con bloques de color sólido e imágenes con límites definidos entre colores.  Los archivos GIF se comprimen, sin que se pierda información durante el proceso de compresión; una imagen descomprimida es exactamente igual que la imagen original.  En un archivo GIF se puede especificar un color como transparente, de forma que la imagen tenga el color de fondo de cualquier página Web en la que se muestre.  Una secuencia de imágenes GIF puede almacenarse en un único archivo para formar un GIF animado.  Los archivos GIF almacenan como máximo 8 bits por píxel, por lo que se limitan a 256 colores.  
  
### JPEG \(Joint Photographic Experts Group, grupo conjunto de expertos en fotografía\)  
 JPEG es un esquema de compresión que funciona muy bien para escenas naturales como fotografías escaneadas.  Durante el proceso de compresión se pierde algo de información, pero la pérdida suele ser imperceptible para el ojo humano.  Los archivos JPEG almacenan 24 bits por píxel, por lo que son capaces de mostrar más de 16 millones de colores.  Los archivos JPEG no admiten transparencia ni animación.  
  
 El nivel de compresión de las imágenes JPEG puede configurarse, pero cuanto mayor sea el nivel de compresión \(archivos más pequeños\), mayor será la pérdida de información.  Una razón de compresión de 20:1 suele generar una imagen que el ojo humano apenas distingue de la imagen original.  En la siguiente ilustración se muestra una imagen BMP y dos imágenes JPEG que se han comprimido a partir de dicha imagen BMP.  La primera imagen JPEG tiene una razón de compresión de 4:1 y la segunda imagen JPEG tiene una razón de compresión en torno a 8:1.  
  
 ![Ejemplos de tipo de archivo](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03.gif "AboutGdip03\_Art03")  
  
 La compresión de archivos JPEG no es apropiada para el dibujo de líneas, bloques de color sólido o límites definidos.  En la siguiente ilustración se muestra un archivo BMP junto con dos archivos JPEG y un archivo GIF.  Los archivos JPEG y el archivo GIF se han comprimido a partir del archivo BMP.  La razón de compresión es de 4:1 para el archivo GIF, de 4:1 para el archivo JPEG más pequeño y de 8:3 para el archivo JPEG más grande.  Tenga en cuenta que el archivo GIF mantiene los límites de las líneas nítidos, mientras que los archivos JPEG tienden a difuminar los límites.  
  
 ![Tipos de archivo](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03a.png "AboutGdip03\_Art03A")  
  
 JPEG es un esquema de compresión, no un formato de archivo.  El formato de intercambio de archivos JPEG \(JFIF\) es un formato de archivos comúnmente utilizado para almacenar y transferir imágenes que se han comprimido conforme al esquema JPEG.  Los archivos JFIF que muestran los exploradores web utilizan la extensión .jpg.  
  
### EXIF \(Exchangeable Image File, archivo de imagen intercambiable\)  
 EXIF es un formato de archivo utilizado para las fotografías que se capturan con cámaras digitales.  Un archivo EXIF contiene una imagen comprimida conforme a la especificación JPEG.  Un archivo EXIF contiene también información acerca de la fotografía \(fecha de toma, velocidad de obturación, tiempo de exposición, etcétera\) e información acerca de la cámara \(fabricante, modelo, etcétera\).  
  
### Formato PNG \(Portable Network Graphics\)  
 El formato PNG conserva muchas de las ventajas del formato GIF pero también aporta más funciones que las del formato GIF.  Al igual que los archivos GIF, los archivos PNG se comprimen sin que se pierda información.  Los archivos PNG pueden almacenar colores con 8, 24 o 48 bits por píxel y escalas de grises con 1, 2, 4, 8 o 16 bits por píxel, mientras que  los archivos GIF sólo pueden utilizar 1, 2, 4 u 8 bits por píxel.  Un archivo PNG puede almacenar también un valor alfa para cada píxel, que especifica el grado de mezcla de ese píxel con el color de fondo.  
  
 El formato PNG supone una mejora con respecto al formato GIF por su capacidad para mostrar una imagen progresivamente; es decir, para mostrar aproximaciones cada vez mejores de la imagen a medida que ésta llega a través de una conexión de red.  Los archivos PNG pueden contener información sobre la corrección de gamma y la corrección de color para que las imágenes puedan representarse con precisión en varios dispositivos de presentación.  
  
### TIFF \(Tag Image File Format, formato de archivo de imágenes con etiquetas\)  
 TIFF es un formato flexible y extensible, compatible con una amplia variedad de plataformas y aplicaciones de procesamiento de imágenes.  Los archivos TIFF pueden almacenar imágenes con un número arbitrario de bits por píxel y pueden emplear varios algoritmos de compresión.  Se pueden almacenar diversas imágenes en un único archivo TIFF de varias páginas.  La información relacionada con la imagen \(marca del escáner, equipo host, tipo de compresión, orientación, muestras por píxel, etcétera\) puede almacenarse en el archivo y organizarse mediante el uso de etiquetas.  El formato TIFF puede extenderse cuando se precise con la aprobación y adición de nuevas etiquetas.  
  
## Vea también  
 <xref:System.Drawing.Image?displayProperty=fullName>   
 <xref:System.Drawing.Bitmap?displayProperty=fullName>   
 <xref:System.Drawing.Imaging.PixelFormat?displayProperty=fullName>   
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)