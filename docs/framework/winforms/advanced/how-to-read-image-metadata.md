---
title: Procedimiento para leer metadatos de imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 3266724503960b8b45cd134dfa5b007a58d578fa
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169811"
---
# <a name="how-to-read-image-metadata"></a>Procedimiento para leer metadatos de imagen
Algunos archivos de imagen contienen metadatos que se pueden leer para determinar las características de la imagen. Por ejemplo, una fotografía digital podría contener metadatos que se pueden leer para determinar la marca y modelo de la cámara empleada para capturar la imagen. Con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede leer los metadatos existentes y también puede escribir los nuevos metadatos para archivos de imagen.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] almacena un elemento individual de los metadatos en un <xref:System.Drawing.Imaging.PropertyItem> objeto. Puede leer el <xref:System.Drawing.Image.PropertyItems%2A> propiedad de un <xref:System.Drawing.Image> objeto para recuperar todos los metadatos de un archivo. El <xref:System.Drawing.Image.PropertyItems%2A> propiedad devuelve una matriz de <xref:System.Drawing.Imaging.PropertyItem> objetos.  
  
 Un <xref:System.Drawing.Imaging.PropertyItem> objeto tiene las siguientes cuatro propiedades: `Id`, `Value`, `Len`, y `Type`.  
  
## <a name="id"></a>Id.  
 Una etiqueta que identifica el elemento de metadatos. Algunos valores que se pueden asignar a <xref:System.Drawing.Imaging.PropertyItem.Id%2A> se muestran en la tabla siguiente.  
  
|Valor hexadecimal|Descripción|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Título de la imagen<br /><br /> Fabricante de equipos<br /><br /> Modelo del equipo<br /><br /> ExifDTOriginal<br /><br /> Tiempo de exposición EXIF<br /><br /> Tabla de luminancia<br /><br /> Tabla cromáticas|  
  
## <a name="value"></a>Valor  
 Una matriz de valores. El formato de los valores viene determinada por la <xref:System.Drawing.Imaging.PropertyItem.Type%2A> propiedad.  
  
## <a name="len"></a>Len  
 La longitud (en bytes) de la matriz de valores que señala el <xref:System.Drawing.Imaging.PropertyItem.Value%2A> propiedad.  
  
## <a name="type"></a>Tipo  
 El tipo de datos de los valores de la matriz que apunta el `Value` propiedad. Los formatos indican por el `Type` se muestran los valores de propiedad en la tabla siguiente  
  
|Valor numérico|Descripción|  
|-------------------|-----------------|  
|1|`Byte`.|  
|2|Una matriz de `Byte` objetos codificada en ASCII|  
|3|Un entero de 16 bits|  
|4|Un entero de 32 bits|  
|5|Una matriz de dos `Byte` objetos que representan un número racional|  
|6|No se utiliza|  
|7|Sin definir|  
|8|No se utiliza|  
|9|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El ejemplo de código siguiente lee y muestra los siete elementos de metadatos en el archivo `FakePhoto.jpg`. El segundo elemento de propiedad (índice 1) en la lista tiene <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (fabricante del equipo) y <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matriz de bytes codificada en ASCII). El ejemplo de código muestra el valor de ese elemento de propiedad.  
  
 El código genera una salida similar al siguiente:  
 
```
 Property Item 0
  
 id: 0x320
  
 type: 2
 
 length: 16 bytes 
  
 Property Item 1
  
 id: 0x10f
  
 type: 2 
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```
  
### <a name="code"></a>Código  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos y pegue este código en el controlador de eventos paint. Debe reemplazar `FakePhoto.jpg` con un nombre de la imagen y la ruta de acceso válida en su sistema e importar el `System.Drawing.Imaging` espacio de nombres.  
  
## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
