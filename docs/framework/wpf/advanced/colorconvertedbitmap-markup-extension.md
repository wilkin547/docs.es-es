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
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="cf230-102">Extensión de marcado ColorConvertedBitmap</span><span class="sxs-lookup"><span data-stu-id="cf230-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="cf230-103">Proporciona una manera de especificar un origen de mapa de bits que no tiene ningún perfil incrustado.</span><span class="sxs-lookup"><span data-stu-id="cf230-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="cf230-104">Contextos de color / perfiles especificados por [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], ya que es el origen de imagen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf230-104">Color contexts / profiles are specified by [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], as is the image source [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="cf230-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="cf230-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="cf230-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="cf230-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="cf230-107">El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del mapa de bits sin perfil.</span><span class="sxs-lookup"><span data-stu-id="cf230-107">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="cf230-108">El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la configuración de perfiles de código fuente.</span><span class="sxs-lookup"><span data-stu-id="cf230-108">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="cf230-109">El [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] de la configuración del perfil de destino</span><span class="sxs-lookup"><span data-stu-id="cf230-109">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf230-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf230-110">Remarks</span></span>  
 <span data-ttu-id="cf230-111">Esta extensión de marcado está pensada para rellenar un conjunto relacionado de valores de propiedad de origen de la imagen como <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf230-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="cf230-112">La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="cf230-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="cf230-113">`ColorConvertedBitmap` (o `ColorConvertedBitmapExtension`) no se puede usar en la sintaxis de elemento de propiedad, porque los valores solo pueden establecerse como valores en el constructor inicial, que es la cadena después del identificador de extensión.</span><span class="sxs-lookup"><span data-stu-id="cf230-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="cf230-114">`ColorConvertedBitmap` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="cf230-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="cf230-115">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="cf230-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="cf230-116">Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="cf230-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="cf230-117">Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="cf230-117">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf230-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf230-118">See also</span></span>
- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="cf230-119">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="cf230-119">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="cf230-120">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="cf230-120">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
