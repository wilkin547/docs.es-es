---
title: Estilos y plantillas insertados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dccf0b274121ff4fe88c9270119a2f631ffcf29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="09e14-102">Estilos y plantillas insertados</span><span class="sxs-lookup"><span data-stu-id="09e14-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="09e14-103">proporciona <xref:System.Windows.Style> objetos y objetos de plantilla (<xref:System.Windows.FrameworkTemplate> subclases) como una manera de definir la apariencia visual de un elemento en recursos, por lo que se pueden usar varias veces.</span><span class="sxs-lookup"><span data-stu-id="09e14-103"> provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="09e14-104">Por esta razón, los atributos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que tenga los tipos <xref:System.Windows.Style> y <xref:System.Windows.FrameworkTemplate> casi siempre realizan referencias de recursos existentes estilos y plantillas, en lugar de definir otros nuevos insertados.</span><span class="sxs-lookup"><span data-stu-id="09e14-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="09e14-105">Limitaciones de plantillas y estilos en línea</span><span class="sxs-lookup"><span data-stu-id="09e14-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="09e14-106">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], propiedades de estilo y plantilla técnicamente pueden establecerse en uno de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="09e14-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="09e14-107">Puede usar la sintaxis de atributo para hacer referencia a un estilo que se ha definido dentro de un recurso, por ejemplo `<` *objeto*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span><span class="sxs-lookup"><span data-stu-id="09e14-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="09e14-108">O bien, puede usar sintaxis de elemento de propiedad para definir un estilo en línea, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="09e14-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="09e14-109">`<`*object*`>`</span><span class="sxs-lookup"><span data-stu-id="09e14-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="09e14-110">`<`*object*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="09e14-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="09e14-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="09e14-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="09e14-112">`</`*object*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="09e14-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="09e14-113">`</`*object*`>`</span><span class="sxs-lookup"><span data-stu-id="09e14-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="09e14-114">El uso de atributos es mucho más común.</span><span class="sxs-lookup"><span data-stu-id="09e14-114">The attribute usage is much more common.</span></span> <span data-ttu-id="09e14-115">Un estilo que se define en línea y recursos no está definidos en necesariamente ámbito es solo el elemento que lo contiene y no se puede volver a usar fácilmente porque no tiene ninguna clave de recurso.</span><span class="sxs-lookup"><span data-stu-id="09e14-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="09e14-116">Por lo general un estilo definido por el recurso es más versátil y útil y es más en consonancia con la ficha general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] principio de modelo de separar la lógica del programa en el código de diseño en el marcado de programación.</span><span class="sxs-lookup"><span data-stu-id="09e14-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="09e14-117">Normalmente no hay ninguna razón para establecer un estilo o una plantilla insertados, incluso si solo desea usar ese estilo o una plantilla en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="09e14-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="09e14-118">Mayoría de los elementos que puede llevar a cabo un estilo o una plantilla también admite una propiedad de contenido y un modelo de contenido.</span><span class="sxs-lookup"><span data-stu-id="09e14-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="09e14-119">Si solo usa el árbol lógico cree mediante estilos o plantillas una vez, sea incluso más fácil rellenar esa propiedad de contenido con los elementos secundarios equivalentes en el marcado directo.</span><span class="sxs-lookup"><span data-stu-id="09e14-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="09e14-120">Los mecanismos de estilo y plantilla Esto podría omitir por completo.</span><span class="sxs-lookup"><span data-stu-id="09e14-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="09e14-121">Otras sintaxis habilitadas por las extensiones de marcado que devuelven un objeto también son posibles para los estilos y plantillas.</span><span class="sxs-lookup"><span data-stu-id="09e14-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="09e14-122">Dos de estas extensiones que tienen los posibles escenarios incluyen [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) y <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="09e14-122">Two such extensions that have possible scenarios include [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e14-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="09e14-123">See Also</span></span>  
 [<span data-ttu-id="09e14-124">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="09e14-124">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
