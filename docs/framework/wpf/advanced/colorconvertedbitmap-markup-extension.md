---
title: Extensión de marcado ColorConvertedBitmap
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: 4f71b90fa00d1aaee0ec5ad43e5a19be03c79c50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647652"
---
# <a name="colorconvertedbitmap-markup-extension"></a>Extensión de marcado ColorConvertedBitmap
Proporciona una manera de especificar un origen de mapa de bits que no tiene ningún perfil incrustado. Contextos de color / perfiles especificados por [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], ya que es el origen de imagen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`imageSource`|El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del mapa de bits sin perfil.|  
|`sourceIIC`|El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la configuración de perfiles de código fuente.|  
|`destinationIIC`|El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la configuración del perfil de destino|  
  
## <a name="remarks"></a>Comentarios  
 Esta extensión de marcado está pensada para rellenar un conjunto relacionado de valores de propiedad de origen de la imagen como <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. `ColorConvertedBitmap` (o `ColorConvertedBitmapExtension`) no se puede usar en la sintaxis de elemento de propiedad, porque los valores solo pueden establecerse como valores en el constructor inicial, que es la cadena después del identificador de extensión.  
  
 `ColorConvertedBitmap` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
