---
title: "Extensión de marcado ColorConvertedBitmap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df6fac332f20d64ddf6569554a75ef96a5536c0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="colorconvertedbitmap-markup-extension"></a>Extensión de marcado ColorConvertedBitmap
Proporciona una manera de especificar un origen de mapa de bits que no tiene un perfil incrustado. Contextos de color / perfiles especificados por [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], ya que es el origen de imagen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`imageSource`|El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del mapa de bits sin perfil.|  
|`sourceIIC`|El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la configuración de perfil de origen.|  
|`destinationIIC`|El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la configuración de perfil de destino|  
  
## <a name="remarks"></a>Comentarios  
 Esta extensión de marcado se ha diseñado para rellenar un conjunto relacionado de valores de propiedad de origen de la imagen como <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. `ColorConvertedBitmap`(o `ColorConvertedBitmapExtension`) no se puede usar en la sintaxis de elemento de propiedad, porque los valores solo pueden establecerse como valores en el constructor inicial, que es la cadena después el identificador de extensión.  
  
 `ColorConvertedBitmap` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>  
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
