---
title: "C&#243;mo: Leer metadatos de imagen | Microsoft Docs"
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
  - "metadatos, elemento de propiedad"
  - "metadatos, leer imagen"
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Leer metadatos de imagen
Algunos archivos de imagen contienen metadatos que se pueden leer para determinar ciertas características de la imagen.  Por ejemplo, una fotografía digital quizás contenga metadatos que se pueden leer para determinar la marca y modelo de la cámara empleada para tomar la imagen.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] permite leer los metadatos existentes y escribir metadatos nuevos en archivos de imagen.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] almacena un metadato en un objeto <xref:System.Drawing.Imaging.PropertyItem>.  La propiedad <xref:System.Drawing.Image.PropertyItems%2A> de un objeto <xref:System.Drawing.Image> se puede leer para recuperar todos los metadatos de un archivo.  La propiedad <xref:System.Drawing.Image.PropertyItems%2A> devuelve una matriz de objetos <xref:System.Drawing.Imaging.PropertyItem>.  
  
 Los objetos <xref:System.Drawing.Imaging.PropertyItem> constan de las cuatro propiedades siguientes: `Id`, `Value`, `Len` y `Type`.  
  
## Id  
 Etiqueta que identifica el elemento de metadato.  En la siguiente tabla se muestran algunos de los valores que pueden asignarse a <xref:System.Drawing.Imaging.PropertyItem.Id%2A>.  
  
|Valor hexadecimal|Descripción|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Título de la imagen<br /><br /> Fabricante del equipo<br /><br /> Modelo del equipo<br /><br /> ExifDTOriginal<br /><br /> Tiempo de exposición en Exif<br /><br /> Tabla de luminancia<br /><br /> Tabla de cromaticidad|  
  
## Valor  
 Matriz de valores.  La propiedad <xref:System.Drawing.Imaging.PropertyItem.Type%2A> determina el formato de los valores.  
  
## Len  
 La longitud \(en bytes\) de una matriz de valores indicada por la propiedad <xref:System.Drawing.Imaging.PropertyItem.Value%2A>.  
  
## Tipo  
 El tipo de datos de los valores contenidos en la matriz indicada por la propiedad `Value`.  La siguiente tabla muestra los formatos indicados por los valores de propiedad `Type`.  
  
|Valor numérico|Descripción|  
|--------------------|-----------------|  
|1|Valor `Byte`|  
|2|Matriz de objetos `Byte` codificada en ASCII|  
|3|Entero de 16 bits|  
|4|Entero de 32 bits|  
|5|Matriz de dos objetos `Byte` que representa un número racional|  
|6|No se utiliza|  
|7|No definido|  
|8|No se utiliza|  
|9|`SLong`|  
|10|`SRational`|  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente se leen y muestran los siete metadatos del archivo `FakePhoto.jpg`.  El segundo elemento de la propiedad \(índice 1\) de la lista tiene <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F \(fabricante del equipo\) y <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 \(matriz de bytes codificada en ASCII\).  El ejemplo de código muestra el valor de ese elemento de propiedad.  
  
 El código produce un resultado similar al siguiente:  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### Código  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  Controle el evento <xref:System.Windows.Forms.Control.Paint> del formulario y pegue este código en el controlador de eventos Paint.  Debe reemplazar `FakePhoto.jpg` con una ruta de acceso y un nombre de imagen válidos en su sistema e importar el espacio de nombres `System.Drawing.Imaging`.  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)