---
title: Tipos de mapas de bits
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
ms.openlocfilehash: f41585ba8816e0b1894a9f01163191848ae391e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663949"
---
# <a name="types-of-bitmaps"></a>Tipos de mapas de bits
Un mapa de bits es una matriz de bits que especifica el color de cada píxel en una matriz rectangular de píxeles. El número de bits asignado a un píxel individual determina el número de colores que se pueden asignar a ese píxel. Por ejemplo, si cada píxel se representa mediante 4 bits, a continuación, un píxel determinado puede asignarse uno de los 16 colores distintos (2 ^ 4 = 16). En la tabla siguiente se muestra algunos ejemplos del número de colores que se pueden asignar a un píxel representado por un número determinado de bits.  
  
|Bits por píxel|Número de colores que se pueden asignar a un píxel|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|8|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 Archivos de disco que almacenan mapas de bits suele contengan uno o más bloques de información que almacenan información como el número de bits por píxel, el número de píxeles en cada fila y el número de filas de la matriz. Este archivo también puede contener una tabla de colores (a veces denominada una paleta de colores). Una tabla de colores asigna números en el mapa de bits de color específicos. La siguiente ilustración muestra una imagen ampliada junto con su tabla de mapa de bits y color. Cada píxel se representa mediante un número de 4 bits, por lo que hay 2 ^ 4 = 16 colores en la tabla de colores. Cada color en la tabla se representa mediante un número de 24 bits: 8 bits para el rojo, 8 bits para el verde y 8 bits para el azul. Los números se muestran en formato hexadecimal (base 16): A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.  
  
 ![Bitmap sample](./media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 Examine el píxel en la fila 3, 5 de la columna de la imagen. El número correspondiente en el mapa de bits es 1. La tabla de colores nos indica que 1 representa el color rojo, por lo que el píxel es rojo. Todas las entradas de la fila superior del mapa de bits son 3. La tabla de colores indica que el 3 representa azul, por lo que todos los píxeles en la fila superior de la imagen son azules.  
  
> [!NOTE]
>  Algunos mapas de bits se almacenan en formato de abajo arriba; los números en la primera fila del mapa de bits corresponden a los píxeles en la fila inferior de la imagen.  
  
 Un mapa de bits que almacena los índices en una tabla de colores se denomina un mapa de bits de paleta indizada. Algunos mapas de bits no es necesario para una tabla de colores. Por ejemplo, si un mapa de bits utiliza 24 bits por píxel, ese mapa de bits puede almacenar los colores a sí mismos en lugar de índices en una tabla de colores. La siguiente ilustración muestra un mapa de bits que almacena colores directamente (24 bits por píxel) en lugar de usar una tabla de colores. La ilustración también muestra una vista ampliada de la imagen correspondiente. En el mapa de bits, FFFFFF representa al blanco, FF0000 representa el rojo, 00FF00 representa el verde y 0000FF representa el azul.  
  
 ![Ejemplo de mapa de bits](./media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>Formatos de archivo de gráficos  
 Hay muchos formatos estándares para guardar los mapas de bits en los archivos de disco. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es compatible con el archivo gráfico formatos descritos en los párrafos siguientes.  
  
### <a name="bmp"></a>BMP  
 BMP es un formato estándar usado por Windows para almacenar imágenes independientes del dispositivo e independiente de la aplicación. El número de bits por píxel (1, 4, 8, 15, 24, 32 o 64) de un archivo BMP determinado se especifica en un encabezado de archivo. Archivos BMP con 24 bits por píxel son comunes. Archivos BMP no suelen comprimirse y, por lo tanto, no son adecuados para la transferencia a través de Internet.  
  
### <a name="graphics-interchange-format-gif"></a>Formato de intercambio de gráficos (GIF)  
 GIF es un formato común para las imágenes que aparecen en las páginas Web. Archivos GIF funcionan bien para dibujos de líneas, imágenes con bloques de color sólido e imágenes con límites nítidos entre colores. Archivos GIF se comprimen, pero no se pierde ninguna información en el proceso de compresión; una imagen descomprimida es exactamente el mismo que el original. Un color en un archivo GIF puede designarse como transparente, para que tenga el color de fondo de cualquier página Web que muestra la imagen. Una secuencia de imágenes GIF se puede almacenar en un único archivo para formar un GIF animado. Archivos GIF almacenan a lo sumo de 8 bits por píxel, por lo que están limitados a 256 colores.  
  
### <a name="joint-photographic-experts-group-jpeg"></a>Joint Photographic Experts Group (JPEG)  
 JPEG es un esquema de compresión que funciona bien para escenas naturales como las fotografías digitalizadas. Se pierde alguna información en el proceso de compresión, pero a menudo la pérdida es imperceptible para el ojo humano. Archivos JPEG almacenan 24 bits por píxel, por lo que son capaces de mostrar más de 16 millones de colores. Archivos JPEG no admiten la transparencia o la animación.  
  
 El nivel de compresión de imágenes JPEG es configurable, pero los niveles más altos de compresión (archivos más pequeños) dar lugar a pérdida de información. A menudo, una razón de compresión de 20:1 genera una imagen que el ojo humano encuentra difícil distinguir de los originales. La siguiente ilustración muestra una imagen BMP y dos imágenes JPEG que se comprimieron desde esa imagen BMP. La primera imagen JPEG tiene una razón de compresión de 4:1 y la segunda imagen JPEG tiene una razón de compresión de aproximadamente 8:1.  
  
 ![Filetype samples](./media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 Compresión JPEG no funcionan bien para dibujos de líneas, bloques de color sólido y los límites definidos. La siguiente ilustración muestra un archivo BMP junto con dos archivos JPEG y un archivo GIF. Los archivos JPEG y el formato GIF se han comprimido a partir del BMP. La razón de compresión es de 4:1 para el archivo GIF, 4:1 para el archivo JPEG más pequeño y 8:3 para el archivo JPEG más grande. Tenga en cuenta que el formato GIF mantiene los límites nítidos a lo largo de las líneas, pero los archivos JPEG tienden a difuminar los límites.  
  
 ![Filetypes](./media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 JPEG es un esquema de compresión, no es un formato de archivo. Formato de intercambio de archivos JPEG (JFIF) es un formato de archivo usado para almacenar y transferir las imágenes que se han comprimido conforme al esquema JPEG. Archivos JFIF que muestran los exploradores Web utilizan la extensión .jpg.  
  
### <a name="exchangeable-image-file-exif"></a>Archivo de imagen intercambiable (EXIF)  
 EXIF es un formato de archivo utilizado para las fotografías que se capturan con cámaras digitales. Un archivo EXIF contiene una imagen que se ha comprimido según la especificación de JPEG. Un archivo EXIF también contiene información acerca de la fotografía (fecha de creación, etc., tiempo de exposición y velocidad de obturación) e información acerca de la cámara (fabricante, modelo y así sucesivamente).  
  
### <a name="portable-network-graphics-png"></a>Formato PNG (Portable Network Graphics)  
 El formato PNG conserva muchas de las ventajas del formato GIF, pero también proporciona capacidades más allá de aquellas de GIF. Como los archivos GIF, archivos PNG se comprimen sin pérdida de información. Archivos PNG pueden almacenar los colores con 8, 24, 48 bits por píxel y escalas de grises con 1, 2, 4, 8 o 16 bits por píxel. En cambio, pueden usar archivos GIF solo 1, 2, 4 o 8 bits por píxel. Un archivo PNG también puede almacenar un valor alfa para cada píxel, que especifica el grado al que el color del píxel se mezcla con el color de fondo.  
  
 PNG mejora su capacidad para mostrar una imagen progresivamente GIF (es decir mostrar mejores y mejores aproximaciones de la imagen tal como llega a través de una conexión de red). Archivos PNG pueden contener información de corrección de color y la corrección de gamma para que las imágenes se pueden representar con precisión en una gran variedad de dispositivos de pantalla.  
  
### <a name="tag-image-file-format-tiff"></a>Tag Image File Format (TIFF)  
 TIFF es un formato flexible y extensible que admite una amplia variedad de plataformas y aplicaciones de procesamiento de imágenes. Archivos TIFF pueden almacenar las imágenes con un número arbitrario de bits por píxel y pueden emplear una variedad de algoritmos de compresión. En un único archivo TIFF de varias páginas se pueden almacenar varias imágenes. Información relacionada con la imagen (marca del escáner, equipo host, tipo de compresión, orientación, muestras por píxel etc.) se puede almacenar en el archivo y organizarse mediante el uso de etiquetas. El formato TIFF puede ampliarse según sea necesario para la aprobación y la adición de nuevas etiquetas.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Image?displayProperty=nameWithType>
- <xref:System.Drawing.Bitmap?displayProperty=nameWithType>
- <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>
- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
