---
title: Estilos y plantillas insertados
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b566e157e2d4a9e9be21a678541bf5d5341a898c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051018"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="ca7d6-102">Estilos y plantillas insertados</span><span class="sxs-lookup"><span data-stu-id="ca7d6-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="ca7d6-103">proporciona <xref:System.Windows.Style> objetos y objetos de plantilla (<xref:System.Windows.FrameworkTemplate> subclases) como una forma de definir la apariencia visual de un elemento en los recursos, por lo que puede utilizarse varias veces.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="ca7d6-104">Por este motivo, los atributos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que toman los tipos <xref:System.Windows.Style> y <xref:System.Windows.FrameworkTemplate> casi siempre que las referencias de recursos en plantillas y estilos existentes en lugar de definir nuevos en línea.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="ca7d6-105">Limitaciones de plantillas y estilos en línea</span><span class="sxs-lookup"><span data-stu-id="ca7d6-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="ca7d6-106">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], técnicamente se pueden establecer propiedades de estilo y plantilla de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="ca7d6-107">Puede usar la sintaxis de atributo para hacer referencia a un estilo que se ha definido dentro de un recurso, por ejemplo `<` *objeto*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="ca7d6-108">O bien, puede usar la sintaxis de elemento de propiedad para definir un estilo en línea, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ca7d6-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="ca7d6-109">`<` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="ca7d6-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="ca7d6-110">`<` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="ca7d6-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="ca7d6-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="ca7d6-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="ca7d6-112">`</` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="ca7d6-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="ca7d6-113">`</` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="ca7d6-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="ca7d6-114">El uso de atributos es mucho más común.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-114">The attribute usage is much more common.</span></span> <span data-ttu-id="ca7d6-115">Un estilo que se definen en línea y no está definido en los recursos se limita necesariamente a solo el elemento contenedor y no se puede volver a utilizar fácilmente porque no tiene ninguna clave de recurso.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="ca7d6-116">En general es más versátil y útil un estilo definido por los recursos y es más en consonancia con el general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] principio del modelo de separar la lógica del programa en el código de diseño en el marcado de programación.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="ca7d6-117">Normalmente, no hay ninguna razón para establecer un estilo o una plantilla insertada, incluso si solo piensa usar ese estilo o plantilla en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="ca7d6-118">La mayoría de los elementos que pueden tomar un estilo o plantilla también admiten una propiedad de contenido y un modelo de contenido.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="ca7d6-119">Si solo usa el árbol lógico cree mediante estilos o plantillas, una vez, es incluso más fácil rellenar esa propiedad de contenido con los elementos secundarios equivalentes en el marcado directo.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="ca7d6-120">Los mecanismos de estilo y plantilla Esto podría omitir por completo.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="ca7d6-121">Otras sintaxis habilitadas por las extensiones de marcado que devuelven un objeto también son posibles para los estilos y plantillas.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="ca7d6-122">Dos de estas extensiones que tienen los posibles escenarios incluyen [TemplateBinding](templatebinding-markup-extension.md) y <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="ca7d6-122">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7d6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca7d6-123">See also</span></span>

- [<span data-ttu-id="ca7d6-124">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="ca7d6-124">Styling and Templating</span></span>](../controls/styling-and-templating.md)
