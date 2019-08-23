---
title: Procedimiento Usar claves de parámetros del sistema
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: edacb4b98ab01f081f668dc3374f6588492210d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918370"
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="bcd8c-102">Procedimiento Usar claves de parámetros del sistema</span><span class="sxs-lookup"><span data-stu-id="bcd8c-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="bcd8c-103">Los recursos del sistema exponen varias métricas del sistema como recursos para ayudar a los desarrolladores a crear efectos visuales coherentes con la configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="bcd8c-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="bcd8c-104"><xref:System.Windows.SystemParameters>es una clase que contiene los valores de parámetro del sistema y las claves de recursos que se enlazan a <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> los <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>valores, por ejemplo, y.</span><span class="sxs-lookup"><span data-stu-id="bcd8c-104"><xref:System.Windows.SystemParameters> is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="bcd8c-105">Las métricas de parámetros del sistema se pueden usar como recursos estáticos o dinámicos.</span><span class="sxs-lookup"><span data-stu-id="bcd8c-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="bcd8c-106">Use un recurso dinámico si quiere que la métrica de parámetros se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático.</span><span class="sxs-lookup"><span data-stu-id="bcd8c-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bcd8c-107">Los recursos dinámicos tienen la palabra *clave* keyword anexada al nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bcd8c-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="bcd8c-108">En el ejemplo siguiente se muestra cómo obtener acceso y usar los recursos dinámicos de parámetros del sistema para aplicar estilo a un botón o personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="bcd8c-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="bcd8c-109">En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] este ejemplo se ajusta el tamaño de un <xref:System.Windows.SystemParameters> botón asignando valores al ancho y alto del botón.</span><span class="sxs-lookup"><span data-stu-id="bcd8c-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcd8c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bcd8c-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="bcd8c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcd8c-111">See also</span></span>

- [<span data-ttu-id="bcd8c-112">Pintar un área con un pincel del sistema</span><span class="sxs-lookup"><span data-stu-id="bcd8c-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="bcd8c-113">Usar SystemFonts</span><span class="sxs-lookup"><span data-stu-id="bcd8c-113">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
- [<span data-ttu-id="bcd8c-114">Usar SystemParameters</span><span class="sxs-lookup"><span data-stu-id="bcd8c-114">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
