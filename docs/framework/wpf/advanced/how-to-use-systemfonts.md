---
title: "Cómo: Utilizar SystemFonts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ce82724a4e9a547b8441628f43621f29eab6307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="24db8-102">Cómo: Utilizar SystemFonts</span><span class="sxs-lookup"><span data-stu-id="24db8-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="24db8-103">Este ejemplo muestra cómo utilizar los recursos estáticos de la <xref:System.Windows.SystemFonts> clase para aplicar estilo a un botón o personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="24db8-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24db8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24db8-104">Example</span></span>  
 <span data-ttu-id="24db8-105">Los recursos del sistema exponen varios valores determinados en el sistema como recursos y propiedades para ayudarle a crear objetos visuales coherentes con la configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="24db8-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="24db8-106"><xref:System.Windows.SystemFonts>es una clase que contiene ambos valores de fuente del sistema como propiedades estáticas y las propiedades que hacen referencia a las claves de recursos que pueden utilizarse para tener acceso a esos valores dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="24db8-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="24db8-107">Por ejemplo, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> es un <xref:System.Windows.SystemFonts> valor, y <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> es una clave de recurso correspondiente.</span><span class="sxs-lookup"><span data-stu-id="24db8-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="24db8-108">En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede utilizar los miembros de <xref:System.Windows.SystemFonts> como propiedades estáticas o referencias de recursos dinámicos (con el valor de propiedad estática como la clave).</span><span class="sxs-lookup"><span data-stu-id="24db8-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="24db8-109">Use una referencia de recursos dinámicos si quiere que la métrica de fuente se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use una referencia de valor estático.</span><span class="sxs-lookup"><span data-stu-id="24db8-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24db8-110">Las claves de recurso tienen el sufijo "Key" anexado al nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="24db8-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="24db8-111">En el ejemplo siguiente se muestra cómo obtener acceso y utilizar las propiedades de <xref:System.Windows.SystemFonts> como valores estáticos para aplicar estilo a un botón o personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="24db8-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="24db8-112">Este ejemplo de marcado se asigna <xref:System.Windows.SystemFonts> valores a un botón.</span><span class="sxs-lookup"><span data-stu-id="24db8-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="24db8-113">Para usar los valores de <xref:System.Windows.SystemFonts> en el código, no es necesario utilizar un valor estático o una referencia de recurso dinámico.</span><span class="sxs-lookup"><span data-stu-id="24db8-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="24db8-114">En su lugar, use las propiedades no son de clave de la <xref:System.Windows.SystemFonts> clase.</span><span class="sxs-lookup"><span data-stu-id="24db8-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="24db8-115">Aunque las propiedades de clave no aparentemente se definen como propiedades estáticas, el comportamiento de tiempo de ejecución de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando está hospedado en el sistema volverá a evaluar las propiedades en tiempo real y que se reflejen correctamente los cambios controlados por el usuario a valores del sistema.</span><span class="sxs-lookup"><span data-stu-id="24db8-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="24db8-116">En el ejemplo siguiente se muestra cómo especificar la configuración de fuente de un botón.</span><span class="sxs-lookup"><span data-stu-id="24db8-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="24db8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="24db8-117">See Also</span></span>  
 <xref:System.Windows.SystemFonts>  
 [<span data-ttu-id="24db8-118">Pintar un área con un pincel del sistema</span><span class="sxs-lookup"><span data-stu-id="24db8-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="24db8-119">Usar SystemParameters</span><span class="sxs-lookup"><span data-stu-id="24db8-119">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="24db8-120">Usar claves de fuentes del sistema</span><span class="sxs-lookup"><span data-stu-id="24db8-120">Use System Fonts Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [<span data-ttu-id="24db8-121">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="24db8-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [<span data-ttu-id="24db8-122">Extensiones de marcado x:Static</span><span class="sxs-lookup"><span data-stu-id="24db8-122">x:Static Markup Extension</span></span>](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [<span data-ttu-id="24db8-123">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="24db8-123">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="24db8-124">DynamicResource (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="24db8-124">DynamicResource Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
