---
title: mc:ProcessContent (Atributo)
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: bcf55668bdc70902e346c401549a88f6ccb9072e
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095130"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="d9773-102">mc:ProcessContent (Atributo)</span><span class="sxs-lookup"><span data-stu-id="d9773-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="d9773-103">Especifica qué elementos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deben seguir teniendo el contenido procesado por los elementos primarios pertinentes, incluso si un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] puede omitir el elemento primario inmediato debido a la especificación de un [atributo MC: ignorable](mc-ignorable-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="d9773-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="d9773-104">El atributo `mc:ProcessContent` admite la compatibilidad de marcado para la asignación de espacios de nombres personalizados y para el control de versiones de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9773-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d9773-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="d9773-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d9773-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="d9773-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9773-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="d9773-107">*ignorablePrefix*</span></span>|<span data-ttu-id="d9773-108">Cualquier cadena de prefijo válida, según la especificación de XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="d9773-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="d9773-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="d9773-109">*ignorableUri*</span></span>|<span data-ttu-id="d9773-110">Cualquier URI válido para designar un espacio de nombres, según la especificación de XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="d9773-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="d9773-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="d9773-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="d9773-112">Un elemento que puede ser omitido por implementaciones de procesador [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], si no se puede resolver el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="d9773-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="d9773-113">*Content*</span><span class="sxs-lookup"><span data-stu-id="d9773-113">*[content]*</span></span>|<span data-ttu-id="d9773-114">*ThisElementCanBeIgnored* está marcado como ignorable.</span><span class="sxs-lookup"><span data-stu-id="d9773-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="d9773-115">Si el procesador omite ese elemento, el *objeto*procesa *[Content]* .</span><span class="sxs-lookup"><span data-stu-id="d9773-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9773-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d9773-116">Remarks</span></span>  
 <span data-ttu-id="d9773-117">De forma predeterminada, un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] omitirá el contenido dentro de un elemento omitido.</span><span class="sxs-lookup"><span data-stu-id="d9773-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="d9773-118">Puede especificar un elemento específico por `mc:ProcessContent`y un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] seguirá procesando el contenido dentro del elemento omitido.</span><span class="sxs-lookup"><span data-stu-id="d9773-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="d9773-119">Esto se suele usar si el contenido está anidado en varias etiquetas, al menos uno de los cuales es ignorable y, al menos, uno de los cuales no se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="d9773-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="d9773-120">Se pueden especificar varios prefijos en el atributo, mediante un separador de espacio, por ejemplo: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="d9773-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="d9773-121">El espacio de nombres `http://schemas.openxmlformats.org/markup-compatibility/2006` define otros elementos y atributos que no están documentados en esta área del SDK.</span><span class="sxs-lookup"><span data-stu-id="d9773-121">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="d9773-122">Para obtener más información, vea [especificación de compatibilidad de marcado XML](https://docs.microsoft.com/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span><span class="sxs-lookup"><span data-stu-id="d9773-122">For more information, see [XML Markup Compatibility Specification](https://docs.microsoft.com/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9773-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9773-123">See also</span></span>

- [<span data-ttu-id="d9773-124">mc:Ignorable (atributo)</span><span class="sxs-lookup"><span data-stu-id="d9773-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="d9773-125">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d9773-125">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
