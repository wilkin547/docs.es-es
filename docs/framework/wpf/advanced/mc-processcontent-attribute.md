---
title: mc:ProcessContent (Atributo)
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: a9af18d1fac9101a75ac16918adf8e86ef7d2ba4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357383"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="d3503-102">mc:ProcessContent (Atributo)</span><span class="sxs-lookup"><span data-stu-id="d3503-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="d3503-103">Especifica qué [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementos todavía deben tener contenido procesado por los elementos primarios pertinentes, incluso si el elemento primario inmediato puede ser omitido por un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador debido a la especificación de [mc: Ignorable (atributo)](mc-ignorable-attribute.md) .</span><span class="sxs-lookup"><span data-stu-id="d3503-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="d3503-104">El `mc:ProcessContent` atributo admite la compatibilidad de marcado para la asignación de espacio de nombres personalizado tanto para [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] control de versiones.</span><span class="sxs-lookup"><span data-stu-id="d3503-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d3503-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="d3503-105">XAML Attribute Usage</span></span>  
  
```  
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
  
## <a name="xaml-values"></a><span data-ttu-id="d3503-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="d3503-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3503-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="d3503-107">*ignorablePrefix*</span></span>|<span data-ttu-id="d3503-108">Cualquier cadena de prefijo válido, según la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="d3503-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="d3503-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="d3503-109">*ignorableUri*</span></span>|<span data-ttu-id="d3503-110">Cualquier URI válido para designar un espacio de nombres, según la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="d3503-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="d3503-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="d3503-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="d3503-112">Un elemento que se puede omitir si [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] las implementaciones de procesadores, si no se puede resolver el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="d3503-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="d3503-113">*[content]*</span><span class="sxs-lookup"><span data-stu-id="d3503-113">*[content]*</span></span>|<span data-ttu-id="d3503-114">*ThisElementCanBeIgnored* está marcado como ignorable.</span><span class="sxs-lookup"><span data-stu-id="d3503-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="d3503-115">Si el procesador omite ese elemento, *[contenido]* procesa *objeto*.</span><span class="sxs-lookup"><span data-stu-id="d3503-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3503-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3503-116">Remarks</span></span>  
 <span data-ttu-id="d3503-117">De forma predeterminada, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador pasará por alto el contenido dentro de un elemento omitido.</span><span class="sxs-lookup"><span data-stu-id="d3503-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="d3503-118">Puede especificar un elemento específico por `mc:ProcessContent`y un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador seguirá procesando el contenido dentro del elemento omitido.</span><span class="sxs-lookup"><span data-stu-id="d3503-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="d3503-119">Esto normalmente se usaría si el contenido está anidado dentro de varias etiquetas, al menos uno de los cuales se puede pasar por alto y al menos uno de los cuales no es puede pasar por alto.</span><span class="sxs-lookup"><span data-stu-id="d3503-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="d3503-120">Se pueden especificar varios prefijos en el atributo, con un espacio como separador, por ejemplo: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="d3503-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="d3503-121">El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área de la [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3503-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="d3503-122">Para obtener más información, consulte [especificación de compatibilidad de marcado XML](https://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="d3503-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3503-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3503-123">See also</span></span>
- [<span data-ttu-id="d3503-124">mc:Ignorable (atributo)</span><span class="sxs-lookup"><span data-stu-id="d3503-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="d3503-125">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d3503-125">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
