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
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="a2b47-102">Extensión de marcado ColorConvertedBitmap</span><span class="sxs-lookup"><span data-stu-id="a2b47-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="a2b47-103">Proporciona una manera de especificar un origen de mapa de bits que no tiene un perfil incrustado.</span><span class="sxs-lookup"><span data-stu-id="a2b47-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="a2b47-104">Los contextos de color/perfiles se especifican mediante el URI, como es el URI de origen de la imagen.</span><span class="sxs-lookup"><span data-stu-id="a2b47-104">Color contexts / profiles are specified by URI, as is the image source URI.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a2b47-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="a2b47-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" ... />
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a2b47-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="a2b47-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="a2b47-107">URI del mapa de bits no perfil.</span><span class="sxs-lookup"><span data-stu-id="a2b47-107">The URI of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="a2b47-108">URI de la configuración del perfil de origen.</span><span class="sxs-lookup"><span data-stu-id="a2b47-108">The URI of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="a2b47-109">El URI de la configuración del perfil de destino.</span><span class="sxs-lookup"><span data-stu-id="a2b47-109">The URI of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2b47-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a2b47-110">Remarks</span></span>  
 <span data-ttu-id="a2b47-111">Esta extensión de marcado está pensada para rellenar un conjunto relacionado de valores de propiedad <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>de origen de imagen como.</span><span class="sxs-lookup"><span data-stu-id="a2b47-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="a2b47-112">La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="a2b47-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="a2b47-113">`ColorConvertedBitmap`(o `ColorConvertedBitmapExtension`) no se puede usar en la sintaxis de elementos de propiedad, porque los valores solo se pueden establecer como valores en el constructor inicial, que es la cadena que sigue al identificador de la extensión.</span><span class="sxs-lookup"><span data-stu-id="a2b47-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="a2b47-114">`ColorConvertedBitmap` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="a2b47-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="a2b47-115">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="a2b47-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="a2b47-116">Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="a2b47-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="a2b47-117">Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="a2b47-117">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b47-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2b47-118">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="a2b47-119">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="a2b47-119">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="a2b47-120">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="a2b47-120">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
