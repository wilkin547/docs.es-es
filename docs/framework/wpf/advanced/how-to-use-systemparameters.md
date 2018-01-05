---
title: "Cómo: Utilizar SystemParameters"
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
helpviewer_keywords: classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec333fbc30374ff6f8e2e7674ab332644ff7aad0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-systemparameters"></a><span data-ttu-id="ea67d-102">Cómo: Utilizar SystemParameters</span><span class="sxs-lookup"><span data-stu-id="ea67d-102">How to: Use SystemParameters</span></span>
<span data-ttu-id="ea67d-103">Este ejemplo muestra cómo obtener acceso y utilizar las propiedades de <xref:System.Windows.SystemParameters> para aplicar estilo a un botón o personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="ea67d-103">This example shows how to access and use the properties of <xref:System.Windows.SystemParameters> in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea67d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea67d-104">Example</span></span>  
 <span data-ttu-id="ea67d-105">Los recursos del sistema exponen varias configuraciones basadas en el sistema como recursos para ayudarle a crear objetos visuales coherentes con la configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="ea67d-105">System resources expose several system based settings as resources in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="ea67d-106"><xref:System.Windows.SystemParameters>es una clase que contiene propiedades de valor del parámetro de sistema y las claves de recursos que se enlazan a los valores.</span><span class="sxs-lookup"><span data-stu-id="ea67d-106"><xref:System.Windows.SystemParameters> is a class that contains both system parameter value properties, and resource keys that bind to the values.</span></span> <span data-ttu-id="ea67d-107">Por ejemplo, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> es un <xref:System.Windows.SystemParameters> valor de propiedad y <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> es la clave de recurso correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ea67d-107">For example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> is a <xref:System.Windows.SystemParameters> property value and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> is the corresponding resource key.</span></span>  
  
 <span data-ttu-id="ea67d-108">En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede utilizar los miembros de <xref:System.Windows.SystemParameters> como el uso de una propiedad estática o referencias de recurso dinámicas (con el valor de propiedad estática como la clave).</span><span class="sxs-lookup"><span data-stu-id="ea67d-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemParameters> as either a static property usage, or a dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="ea67d-109">Use una referencia de recursos dinámicos si quiere que el valor basado en el sistema se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático.</span><span class="sxs-lookup"><span data-stu-id="ea67d-109">Use a dynamic resource reference if you want the system based value to update automatically while the application runs; otherwise, use a static reference.</span></span> <span data-ttu-id="ea67d-110">Las claves de recurso tienen el sufijo `Key` anexado al nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ea67d-110">Resource keys have the suffix `Key` appended to the property name.</span></span>  
  
 <span data-ttu-id="ea67d-111">En el ejemplo siguiente se muestra cómo obtener acceso y utilizar los valores estáticos de <xref:System.Windows.SystemParameters> para aplicar estilo a un botón o personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="ea67d-111">The following example shows how to access and use the static values of <xref:System.Windows.SystemParameters> to style or customize a button.</span></span> <span data-ttu-id="ea67d-112">Este ejemplo de marcado se cambia el tamaño de un botón mediante la aplicación <xref:System.Windows.SystemParameters> valores a un botón.</span><span class="sxs-lookup"><span data-stu-id="ea67d-112">This markup example sizes a button by applying <xref:System.Windows.SystemParameters> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 <span data-ttu-id="ea67d-113">Para usar los valores de <xref:System.Windows.SystemParameters> en el código, no es necesario utilizar referencias estáticas o referencias de recursos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="ea67d-113">To use the values of <xref:System.Windows.SystemParameters> in code, you do not have to use either static references or dynamic resource references.</span></span> <span data-ttu-id="ea67d-114">En su lugar, use los valores de la <xref:System.Windows.SystemParameters> clase.</span><span class="sxs-lookup"><span data-stu-id="ea67d-114">Instead, use the values of the <xref:System.Windows.SystemParameters> class.</span></span> <span data-ttu-id="ea67d-115">Aunque las propiedades de clave no aparentemente se definen como propiedades estáticas, el comportamiento en tiempo de ejecución de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando está hospedado en el sistema se vuelve a evaluar las propiedades en tiempo real, y de correctamente explicar los cambios controlados por el usuario a valores del sistema.</span><span class="sxs-lookup"><span data-stu-id="ea67d-115">Although the non-key properties are apparently defined as static properties, the runtime behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in realtime, and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="ea67d-116">En el ejemplo siguiente se muestra cómo establecer el ancho y alto de un botón mediante el uso de <xref:System.Windows.SystemParameters> valores.</span><span class="sxs-lookup"><span data-stu-id="ea67d-116">The following example shows how to set the width and height of a button by using <xref:System.Windows.SystemParameters> values.</span></span>  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="ea67d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea67d-117">See Also</span></span>  
 <xref:System.Windows.SystemParameters>  
 [<span data-ttu-id="ea67d-118">Pintar un área con un pincel del sistema</span><span class="sxs-lookup"><span data-stu-id="ea67d-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="ea67d-119">Usar SystemFonts</span><span class="sxs-lookup"><span data-stu-id="ea67d-119">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [<span data-ttu-id="ea67d-120">Usar claves de parámetros del sistema</span><span class="sxs-lookup"><span data-stu-id="ea67d-120">Use System Parameters Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [<span data-ttu-id="ea67d-121">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="ea67d-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
