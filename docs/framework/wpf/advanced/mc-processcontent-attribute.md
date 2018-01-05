---
title: mc:ProcessContent (Atributo)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fe43e2450c35d976db7a188f854f7864f298afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="e57c4-102">mc:ProcessContent (Atributo)</span><span class="sxs-lookup"><span data-stu-id="e57c4-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="e57c4-103">Especifica qué [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementos todavía deben tener contenido procesado por los elementos primarios pertinentes, aunque se puede omitir el elemento primario inmediato por un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador debido a la especificación de [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) .</span><span class="sxs-lookup"><span data-stu-id="e57c4-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).</span></span> <span data-ttu-id="e57c4-104">El `mc:ProcessContent` atributo admite la compatibilidad de marcado para la asignación de espacio de nombres personalizado y para [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] control de versiones.</span><span class="sxs-lookup"><span data-stu-id="e57c4-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="e57c4-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="e57c4-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="e57c4-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="e57c4-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e57c4-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="e57c4-107">*ignorablePrefix*</span></span>|<span data-ttu-id="e57c4-108">Cualquier cadena de prefijo, según la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="e57c4-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="e57c4-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="e57c4-109">*ignorableUri*</span></span>|<span data-ttu-id="e57c4-110">Cualquier URI válido para designar un espacio de nombres, según la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="e57c4-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="e57c4-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="e57c4-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="e57c4-112">Un elemento que se puede omitir si [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] las implementaciones del procesador, si no se puede resolver el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="e57c4-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="e57c4-113">*[contenido]*</span><span class="sxs-lookup"><span data-stu-id="e57c4-113">*[content]*</span></span>|<span data-ttu-id="e57c4-114">*ThisElementCanBeIgnored* se marca puede pasar por alto.</span><span class="sxs-lookup"><span data-stu-id="e57c4-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="e57c4-115">Si el procesador de impresión omite ese elemento, *[contenido]* procesa *objeto*.</span><span class="sxs-lookup"><span data-stu-id="e57c4-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e57c4-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e57c4-116">Remarks</span></span>  
 <span data-ttu-id="e57c4-117">De forma predeterminada, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador omitirá el contenido incluido en un elemento omitido.</span><span class="sxs-lookup"><span data-stu-id="e57c4-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="e57c4-118">Puede especificar un elemento específico por `mc:ProcessContent`y un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador continuará procesando el contenido dentro del elemento omitido.</span><span class="sxs-lookup"><span data-stu-id="e57c4-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="e57c4-119">Esto lo que normalmente se utiliza si el contenido está anidado dentro de varias etiquetas, al menos uno de los cuales se pueden pasar por alto y al menos uno de los cuales no pueden pasar por alto.</span><span class="sxs-lookup"><span data-stu-id="e57c4-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="e57c4-120">Se pueden especificar varios prefijos en el atributo, con un espacio como separador, por ejemplo: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="e57c4-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="e57c4-121">El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área de la [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e57c4-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="e57c4-122">Para obtener más información, consulte [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="e57c4-122">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57c4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e57c4-123">See Also</span></span>  
 [<span data-ttu-id="e57c4-124">mc:Ignorable (atributo)</span><span class="sxs-lookup"><span data-stu-id="e57c4-124">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [<span data-ttu-id="e57c4-125">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="e57c4-125">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
