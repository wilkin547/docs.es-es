---
title: 'Cómo: Leer metadatos de imagen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: e2b56175e625281a920c390e5feb4238e3cb7f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182516"
---
# <a name="how-to-read-image-metadata"></a>Cómo: Leer metadatos de imagen

Algunos archivos de imagen contienen metadatos que puede leer para determinar las características de la imagen. Por ejemplo, una fotografía digital puede contener metadatos que puede leer para determinar la imagen y el modelo de la cámara utilizada para capturar la imagen. Con GDI+, puede leer los metadatos existentes y también puede escribir nuevos metadatos en archivos de imagen.

GDI+GDI+ almacena un <xref:System.Drawing.Imaging.PropertyItem> fragmento individual de metadatos en un objeto. Puede leer <xref:System.Drawing.Image.PropertyItems%2A> la propiedad <xref:System.Drawing.Image> de un objeto para recuperar todos los metadatos de un archivo. La <xref:System.Drawing.Image.PropertyItems%2A> propiedad devuelve <xref:System.Drawing.Imaging.PropertyItem> una matriz de objetos.

Un <xref:System.Drawing.Imaging.PropertyItem> objeto tiene las `Id`cuatro `Value` `Len`propiedades `Type`siguientes: , , , y .

## <a name="id"></a>Identificador

Etiqueta que identifica el elemento de metadatos. Algunos valores a <xref:System.Drawing.Imaging.PropertyItem.Id%2A> los que se puede asignar se muestran en la tabla siguiente:

|Valor hexadecimal|Descripción|
|-----------------------|-----------------|
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Título de la imagen<br /><br /> Fabricante de equipos<br /><br /> Modelo de equipo<br /><br /> ExifDTOriginal<br /><br /> Tiempo de exposición de Exif<br /><br /> Mesa de luminancia<br /><br /> Mesa de crominancia|

## <a name="value"></a>Value

Matriz de valores . El formato de los valores <xref:System.Drawing.Imaging.PropertyItem.Type%2A> viene determinado por la propiedad.

## <a name="len"></a>Len

La longitud (en bytes) de la matriz <xref:System.Drawing.Imaging.PropertyItem.Value%2A> de valores a la que apunta la propiedad.

## <a name="type"></a>Tipo

El tipo de datos de los valores `Value` de la matriz a la que apunta la propiedad. Los formatos indicados por los `Type` valores de propiedad se muestran en la tabla siguiente:

|Valor numérico|Descripción|
|-------------------|-----------------|
|1|Un tipo de datos `Byte`|
|2|Una matriz `Byte` de objetos codificados como ASCII|
|3|Un entero de 16 bits|
|4|Un entero de 32 bits|
|5|Matriz de `Byte` dos objetos que representan un número racional|
|6|No se usa|
|7|No definido|
|8|No se usa|
|9|`SLong`|
|10|`SRational`|

## <a name="example"></a>Ejemplo
  
En el ejemplo de código siguiente se lee `FakePhoto.jpg`y se muestran los siete fragmentos de metadatos del archivo. El segundo elemento de propiedad (índice <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 1) de la lista tiene <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 0x010F (fabricante del equipo) y 2 (matriz de bytes codificada en ASCII). En el ejemplo de código se muestra el valor de ese elemento de propiedad.

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

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

## <a name="compiling-the-code"></a>Compilar el código

El ejemplo anterior está diseñado para su uso <xref:System.Windows.Forms.PaintEventArgs> `e`con formularios Windows Forms, y requiere , que es un parámetro del <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Controle el <xref:System.Windows.Forms.Control.Paint> evento del formulario y pegue este código en el controlador de eventos paint. Debe reemplazar `FakePhoto.jpg` con un nombre de imagen y `System.Drawing.Imaging` una ruta de acceso válidas en el sistema e importar el espacio de nombres.

## <a name="see-also"></a>Consulte también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
