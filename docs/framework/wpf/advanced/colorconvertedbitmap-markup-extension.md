---
title: "Extensi&#243;n de marcado ColorConvertedBitmap | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ColorConvertedBitmap (extensión de marcado)"
  - "XAML, ColorConvertedBitmap (extensión de marcado)"
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Extensi&#243;n de marcado ColorConvertedBitmap
Proporciona una manera de especificar un origen de mapa de bits que no tiene un perfil incrustado.  Los contextos y perfiles de los colores se especifican mediante [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], como el [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de origen de la imagen.  
  
## Uso de atributos XAML  
  
```  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`imageSource`|[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del mapa de bits sin perfil.|  
|`sourceIIC`|[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la configuración del perfil de origen.|  
|`destinationIIC`|[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la configuración del perfil de destino|  
  
## Comentarios  
 Esta extensión de marcado se ha diseñado para rellenar un conjunto relacionado de valores de propiedades del origen de la imagen, como <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.  
  
 La sintaxis de atributo es la que se usa más a menudo con esta extensión de marcado.  `ColorConvertedBitmap` \(o `ColorConvertedBitmapExtension`\) no se puede utilizar en la sintaxis de elementos de propiedad, porque los valores únicamente se pueden establecer como tales en el constructor inicial, que es la cadena que sigue al identificador de la extensión.  
  
 `ColorConvertedBitmap` es una extensión de marcado.  Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.  Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.  Para obtener más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Vea también  
 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)