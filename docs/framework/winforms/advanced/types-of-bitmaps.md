---
title: Tipos de mapas de bits
description: Obtenga información sobre los tipos de mapas de bits y los formatos de archivo de gráficos GDI+ compatibles, incluidos BMP, JPG, GIF, PNG y TIFF.
ms.date: 03/30/2017
helpviewer_keywords:
- jpeg files
- TIFF files
- gif files
- Graphics Interchange Format
- Joint Photographic Experts Group
- .jpeg files
- .gif files
- graphics [Windows Forms], file formats
- images [Windows Forms], file formats
- Portable Network Graphics
- .bmp files
- EXIF file format
- PNG files
- pictures [Windows Forms], file formats
- Tag Image File Format
- bitmaps [Windows Forms], file format
- Exchangeable Image File
ms.assetid: 6be085a2-2c13-47c8-b80a-c18b32777d8d
ms.openlocfilehash: 09b74ef476467b0bba5aac1f58db278b3898ef17
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174684"
---
# <a name="types-of-bitmaps"></a>Tipos de mapas de bits
Un mapa de bits es una matriz de bits que especifican el color de cada píxel de una matriz rectangular de píxeles. El número de bits dedicado a un píxel individual determina el número de colores que se pueden asignar a ese píxel. Por ejemplo, si cada píxel se representa mediante 4 bits, a un píxel determinado se le puede asignar uno de 16 colores diferentes (2 ^ 4 = 16). En la tabla siguiente se muestran algunos ejemplos del número de colores que se pueden asignar a un píxel representado por un número determinado de bits.  
  
|Bits por píxel|Número de colores que se pueden asignar a un píxel|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|8|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 Los archivos de disco que almacenan mapas de bits normalmente contienen uno o más bloques de información que almacenan información como el número de bits por píxel, el número de píxeles de cada fila y el número de filas de la matriz. Este tipo de archivo también puede contener una tabla de colores (a veces denominada paleta de colores). Una tabla de colores asigna números en el mapa de bits a colores específicos. En la ilustración siguiente se muestra una imagen ampliada junto con su mapa de bits y tabla de colores. Cada píxel se representa mediante un número de 4 bits, por lo que hay 2 ^ 4 = 16 colores en la tabla de colores. Cada color de la tabla se representa mediante un número de 24 bits: 8 bits para rojo, 8 bits para verde y 8 bits para azul. Los números se muestran en formato hexadecimal (base 16): A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.  
  
 ![Ejemplo de mapa de bits](./media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 Fíjese en el píxel de la fila 3, columna 5 de la imagen. El número correspondiente en el mapa de bits es 1. La tabla de colores nos indica que 1 representa el color rojo, de modo que el píxel es rojo. Todas las entradas de la fila superior del mapa de bits son 3. La tabla de colores nos indica que 3 representa el azul, por lo que todos los píxeles de la fila superior de la imagen son azules.  
  
> [!NOTE]
> Algunos mapas de bits se almacenan en formato ascendente; los números de la primera fila del mapa de bits corresponden a los píxeles de la fila inferior de la imagen.  
  
 Un mapa de bits que almacena índices en una tabla de colores se denomina mapa de bits indexado por una paleta. Algunos mapas de bits no tienen necesidad de una tabla de colores. Por ejemplo, si un mapa de bits usa 24 bits por píxel, dicho mapa de bits puede almacenar los propios colores en lugar de los índices en una tabla de colores. En la ilustración siguiente se muestra un mapa de bits que almacena los colores directamente (24 bits por píxel) en lugar de usar una tabla de colores. La ilustración también muestra una vista ampliada de la imagen correspondiente. En el mapa de bits, FFFFFF representa el blanco, FF0000 representa rojo, 00FF00 representa el verde y 0000FF representa el azul.  
  
 ![Ejemplo de mapa de bits](./media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>Formatos de archivo de gráficos  
 Existen muchos formatos estándar para guardar mapas de bits en archivos de disco. GDI+ es compatible con los formatos de archivo de gráficos descritos en los párrafos siguientes.  
  
### <a name="bmp"></a>BMP  
 BMP es un formato estándar que usa Windows para almacenar imágenes independientes del dispositivo e independientes de la aplicación. El número de bits por píxel (1, 4, 8, 15, 24, 32 o 64) de un archivo BMP determinado se especifica en un encabezado de archivo. Los archivos BMP con 24 bits por píxel son comunes. Los archivos BMP normalmente no se comprimen y, por lo tanto, no son adecuados para la transferencia a través de Internet.  
  
### <a name="graphics-interchange-format-gif"></a>Formato de intercambio de gráficos (GIF)  
 GIF es un formato común para las imágenes que aparecen en páginas Web. Los archivos GIF funcionan bien para los dibujos de líneas, imágenes con bloques de color sólido e imágenes con límites nítidos entre los colores. Los archivos GIF se comprimen, pero no se pierde información en el proceso de compresión; una imagen descomprimida es exactamente la misma que la original. Un color de un GIF puede designarse como transparente, de modo que la imagen tendrá el color de fondo de cualquier página web que la muestre. Se puede almacenar una secuencia de imágenes GIF en un solo archivo para formar un GIF animado. Los archivos GIF almacenan a lo sumo 8 bits por píxel, por lo que están limitados a 256 colores.  
  
### <a name="joint-photographic-experts-group-jpeg"></a>Formato JPEG (Joint Photographic Experts Group)  
 JPEG es un esquema de compresión que funciona bien con escenas naturales como fotografías digitalizadas. Parte de la información se pierde en el proceso de compresión, pero a menudo la pérdida es imperceptible para el ojo humano. Los archivos JPEG almacenan 24 bits por píxel, por lo que son capaces de mostrar más de 16 millones colores. Los archivos JPEG no admiten transparencia ni animación.  
  
 El nivel de compresión de las imágenes JPEG es configurable, pero los niveles de compresión más altos (archivos más pequeños) producen más pérdida de información. Una razón de compresión 20:1 suele generar una imagen que el ojo humano encuentra difícil de distinguir de la original. En la ilustración siguiente se muestra una imagen BMP y dos imágenes JPEG que se comprimieron a partir de esa imagen BMP. La primera JPEG tiene una relación de compresión de 4:1 y la segunda tiene una relación de compresión de aproximadamente 8:1.  
  
 ![Ejemplos de tipo de archivo](./media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 La compresión JPEG no funciona bien para los dibujos de líneas, los bloques de color sólido y los límites nítidos. En la ilustración siguiente se muestra un BMP junto con dos archivos JPEG y un GIF. Los archivos JPEG y el GIF se han comprimido a partir del BMP. La razón de compresión es 4:1 para el archivo GIF, 4:1 para el archivo JPEG más pequeño y 8:3 para el archivo JPEG más grande. Tenga en cuenta que el GIF mantiene los límites nítidos a lo largo de las líneas, pero los archivos JPEG tienden a desenfocar los límites.  
  
 ![Tipos de archivo](./media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 JPEG es un esquema de compresión, no un formato de archivo. El formato de intercambio de archivos JPEG (JFIF) es un formato de archivo que se usa normalmente para almacenar y transferir imágenes que se han comprimido según el esquema JPEG. Los archivos JFIF mostrados por los exploradores web utilizan la extensión. jpg.  
  
### <a name="exchangeable-image-file-exif"></a>Archivo de imagen intercambiable (EXIF)  
 EXIF es un formato de archivo que se usa para las fotografías capturadas por cámaras digitales. Un archivo EXIF contiene una imagen que se comprime según la especificación JPEG. Un archivo EXIF también contiene información acerca de la fotografía (fecha de toma, velocidad de obturación, tiempo de exposición, etc.) e información sobre la cámara (fabricante, modelo, etc.).  
  
### <a name="portable-network-graphics-png"></a>Formato PNG (Portable Network Graphics)  
 El formato PNG conserva muchas de las ventajas del formato GIF, pero también proporciona capacidades más allá de las de GIF. Al igual que los archivos GIF, los archivos PNG se comprimen sin pérdida de información. Los archivos PNG pueden almacenar colores con 8, 24 o 48 bits por píxel y escalas de grises con 1, 2, 4, 8 o 16 bits por píxel. En cambio, los archivos GIF solo pueden usar 1, 2, 4 u 8 bits por píxel. Un archivo PNG también puede almacenar un valor alfa para cada píxel, que especifica el grado en el que el color de ese píxel se combina con el color de fondo.  
  
 PNG mejora el formato GIF en su capacidad para mostrar progresivamente una imagen (es decir, para mostrar mejores y mejores aproximaciones de la imagen a medida que llega a través de una conexión de red). Los archivos PNG pueden contener información de corrección de color y corrección de gamma para que las imágenes se puedan representar con precisión en una variedad de dispositivos de pantalla.  
  
### <a name="tag-image-file-format-tiff"></a>Formato de archivo de imagen de etiqueta (TIFF)  
 TIFF es un formato flexible y ampliable que es compatible con una amplia variedad de plataformas y aplicaciones de procesamiento de imágenes. Los archivos TIFF pueden almacenar imágenes con un número arbitrario de bits por píxel y pueden emplear diversos algoritmos de compresión. Se pueden almacenar varias imágenes en un único archivo TIFF de varias páginas. La información relacionada con la imagen (la marca del escáner, el equipo host, el tipo de compresión, la orientación, los ejemplos por píxel, etc.) puede almacenarse en el archivo y organizarse mediante el uso de etiquetas. El formato TIFF puede extenderse según sea necesario mediante la aprobación y la adición de etiquetas nuevas.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Image?displayProperty=nameWithType>
- <xref:System.Drawing.Bitmap?displayProperty=nameWithType>
- <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>
- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
