---
title: Extensión de marcado ColorConvertedBitmap
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: a5b491723a036c1b1fd0bb61736e6f2ee53fbcd3
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141229"
---
# <a name="colorconvertedbitmap-markup-extension"></a>Extensión de marcado ColorConvertedBitmap
Proporciona una manera de especificar un origen de mapa de bits que no tiene un perfil incrustado. Los contextos de color/perfiles se especifican mediante el URI, como es el URI de origen de la imagen.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" ... />
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`imageSource`|URI del mapa de bits no perfil.|  
|`sourceIIC`|URI de la configuración del perfil de origen.|  
|`destinationIIC`|El URI de la configuración del perfil de destino.|  
  
## <a name="remarks"></a>Observaciones  
 Esta extensión de marcado está pensada para rellenar un conjunto relacionado de valores de propiedad <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>de origen de imagen como.  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. `ColorConvertedBitmap`(o `ColorConvertedBitmapExtension`) no se puede usar en la sintaxis de elementos de propiedad, porque los valores solo se pueden establecer como valores en el constructor inicial, que es la cadena que sigue al identificador de la extensión.  
  
 `ColorConvertedBitmap` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Información general sobre imágenes](../graphics-multimedia/imaging-overview.md)
