---
title: "Cómo: Utilizar claves de parámetros del sistema"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2b5f45f386c58b0577a2716c6fe1396f4c44f4ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="93967-102">Cómo: Utilizar claves de parámetros del sistema</span><span class="sxs-lookup"><span data-stu-id="93967-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="93967-103">Los recursos del sistema exponen varias métricas del sistema como recursos para ayudar a los desarrolladores a crear efectos visuales coherentes con la configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="93967-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="93967-104"><xref:System.Windows.SystemParameters>es una clase que contiene los valores de parámetro del sistema y las claves de recursos que se enlazan a los valores, por ejemplo, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> y <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="93967-104"><xref:System.Windows.SystemParameters> is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="93967-105">Las métricas de parámetros del sistema se pueden usar como recursos estáticos o dinámicos.</span><span class="sxs-lookup"><span data-stu-id="93967-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="93967-106">Use un recurso dinámico si quiere que la métrica de parámetros se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático.</span><span class="sxs-lookup"><span data-stu-id="93967-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93967-107">Los recursos dinámicos tienen la palabra clave *clave* anexado al nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="93967-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="93967-108">En el ejemplo siguiente se muestra cómo obtener acceso y usar los recursos dinámicos de parámetros del sistema para aplicar estilo a un botón o personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="93967-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="93967-109">Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en el ejemplo se cambia el tamaño de un botón mediante la asignación de <xref:System.Windows.SystemParameters> valores al alto y ancho del botón.</span><span class="sxs-lookup"><span data-stu-id="93967-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93967-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93967-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="93967-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="93967-111">See Also</span></span>  
 [<span data-ttu-id="93967-112">Pintar un área con un pincel del sistema</span><span class="sxs-lookup"><span data-stu-id="93967-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="93967-113">Usar SystemFonts</span><span class="sxs-lookup"><span data-stu-id="93967-113">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [<span data-ttu-id="93967-114">Usar SystemParameters</span><span class="sxs-lookup"><span data-stu-id="93967-114">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
