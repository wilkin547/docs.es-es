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
ms.openlocfilehash: 8294bc6596c408160a50d9d7d5e6154f66025c73
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988569"
---
# <a name="how-to-read-image-metadata"></a>Procedimiento para leer metadatos de imagen
Algunos archivos de imagen contienen metadatos que se pueden leer para determinar las características de la imagen. Por ejemplo, una fotografía digital podría contener metadatos que puede leer para determinar la marca y el modelo de la cámara utilizada para capturar la imagen. Con GDI+, puede leer los metadatos existentes y también puede escribir nuevos metadatos en archivos de imagen.  
  
 GDI+ almacena un elemento individual de metadatos en <xref:System.Drawing.Imaging.PropertyItem> un objeto. Puede leer la <xref:System.Drawing.Image.PropertyItems%2A> propiedad de un <xref:System.Drawing.Image> objeto para recuperar todos los metadatos de un archivo. La <xref:System.Drawing.Image.PropertyItems%2A> propiedad devuelve una matriz de <xref:System.Drawing.Imaging.PropertyItem> objetos.  
  
 Un <xref:System.Drawing.Imaging.PropertyItem> objeto tiene las cuatro propiedades siguientes: `Id`, `Value`, `Len`y `Type`.  
  
## <a name="id"></a>Id  
 Etiqueta que identifica el elemento de metadatos. En la tabla siguiente se muestran algunos <xref:System.Drawing.Imaging.PropertyItem.Id%2A> valores que se pueden asignar a.  
  
|Valor hexadecimal|DESCRIPCIÓN|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Título de la imagen<br /><br /> Fabricante de equipos<br /><br /> Modelo de equipo<br /><br /> ExifDTOriginal<br /><br /> Hora de exposición de Exif<br /><br /> Tabla de luminancia<br /><br /> Tabla de crominancia|  
  
## <a name="value"></a>Valor  
 Matriz de valores. El formato de los valores viene determinado por la <xref:System.Drawing.Imaging.PropertyItem.Type%2A> propiedad.  
  
## <a name="len"></a>Len  
 La longitud (en bytes) de la matriz de valores a la que apunta <xref:System.Drawing.Imaging.PropertyItem.Value%2A> la propiedad.  
  
## <a name="type"></a>Type  
 El tipo de datos de los valores de la matriz a la que `Value` apunta la propiedad. Los formatos indicados por `Type` los valores de propiedad se muestran en la tabla siguiente.  
  
|Valor numérico|DESCRIPCIÓN|  
|-------------------|-----------------|  
|1|`Byte`.|  
|2|Matriz de `Byte` objetos codificados como ASCII|  
|3|Entero de 16 bits|  
|4|Un entero de 32 bits|  
|5|Matriz de dos `Byte` objetos que representan un número racional|  
|6|No se utiliza|  
|7|Sin definir|  
|8|No se utiliza|  
|9|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>DESCRIPCIÓN  
 En el ejemplo de código siguiente se lee y se muestran los siete fragmentos de `FakePhoto.jpg`metadatos del archivo. El segundo elemento de propiedad (Índice 1) de la lista <xref:System.Drawing.Imaging.PropertyItem.Id%2A> tiene 0x010F (fabricante del equipo <xref:System.Drawing.Imaging.PropertyItem.Type%2A> ) y 2 (matriz de bytes codificada en ASCII). En el ejemplo de código se muestra el valor de ese elemento de propiedad.  
  
 El código genera una salida similar a la siguiente:  
 
```output
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
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que <xref:System.Windows.Forms.Control.Paint> es un parámetro del controlador de eventos. Controle el evento <xref:System.Windows.Forms.Control.Paint> del formulario y péguelo en el controlador de eventos Paint. Debe reemplazar `FakePhoto.jpg` por un nombre de imagen y una ruta de acceso válidas en el `System.Drawing.Imaging` sistema e importar el espacio de nombres.  
  
## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
