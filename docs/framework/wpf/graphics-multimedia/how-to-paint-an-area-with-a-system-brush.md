---
title: Procedimiento Pintar un área con un pincel del sistema
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: 6977410a596a943a23c3841e80edf4cfed1bf6b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644942"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="85efe-102">Procedimiento Pintar un área con un pincel del sistema</span><span class="sxs-lookup"><span data-stu-id="85efe-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="85efe-103">El <xref:System.Windows.SystemColors> clase proporciona acceso a los pinceles del sistema y los colores, como <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, y <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span><span class="sxs-lookup"><span data-stu-id="85efe-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="85efe-104">Un pincel del sistema es un <xref:System.Windows.Media.SolidColorBrush> objeto que pinta un área con el color del sistema especificado.</span><span class="sxs-lookup"><span data-stu-id="85efe-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="85efe-105">Un pincel del sistema siempre produce un relleno sólido; no puede usarse para crear un degradado.</span><span class="sxs-lookup"><span data-stu-id="85efe-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="85efe-106">Puede utilizar los pinceles del sistema como un recurso estático o dinámico.</span><span class="sxs-lookup"><span data-stu-id="85efe-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="85efe-107">Utilice un recurso dinámico si desea que el pincel se actualice automáticamente si el usuario cambia el pincel del sistema mientras se ejecuta la aplicación; de lo contrario, utilice un recurso estático.</span><span class="sxs-lookup"><span data-stu-id="85efe-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="85efe-108">La clase SystemColors contiene varias propiedades estáticas que siguen una convención de nomenclatura estricta:</span><span class="sxs-lookup"><span data-stu-id="85efe-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="85efe-109">*\<SystemColor>* Brush</span><span class="sxs-lookup"><span data-stu-id="85efe-109">*\<SystemColor>* Brush</span></span>  
  
     <span data-ttu-id="85efe-110">Obtiene una referencia estática a un <xref:System.Windows.Media.SolidColorBrush> del color del sistema especificado.</span><span class="sxs-lookup"><span data-stu-id="85efe-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="85efe-111">*\<SystemColor>* BrushKey</span><span class="sxs-lookup"><span data-stu-id="85efe-111">*\<SystemColor>* BrushKey</span></span>  
  
     <span data-ttu-id="85efe-112">Obtiene una referencia dinámica a un <xref:System.Windows.Media.SolidColorBrush> del color del sistema especificado.</span><span class="sxs-lookup"><span data-stu-id="85efe-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="85efe-113">*\<SystemColor>* Color</span><span class="sxs-lookup"><span data-stu-id="85efe-113">*\<SystemColor>* Color</span></span>  
  
     <span data-ttu-id="85efe-114">Obtiene una referencia estática a una <xref:System.Windows.Media.Color> estructura de color del sistema especificado.</span><span class="sxs-lookup"><span data-stu-id="85efe-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="85efe-115">*\<SystemColor>* ColorKey</span><span class="sxs-lookup"><span data-stu-id="85efe-115">*\<SystemColor>* ColorKey</span></span>  
  
     <span data-ttu-id="85efe-116">Obtiene una referencia dinámica a la <xref:System.Windows.Media.Color> estructura de color del sistema especificado.</span><span class="sxs-lookup"><span data-stu-id="85efe-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="85efe-117">Un color del sistema es un <xref:System.Windows.Media.Color> estructura que se puede usar para configurar un pincel.</span><span class="sxs-lookup"><span data-stu-id="85efe-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="85efe-118">Por ejemplo, puede crear un degradado con los colores del sistema estableciendo el <xref:System.Windows.Media.GradientStop.Color%2A> las propiedades de un <xref:System.Windows.Media.LinearGradientBrush> delimitadores de degradado del objeto con los colores del sistema.</span><span class="sxs-lookup"><span data-stu-id="85efe-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="85efe-119">Para obtener un ejemplo, vea [usar colores del sistema en un degradado](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="85efe-119">For an example, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85efe-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85efe-120">Example</span></span>  
 <span data-ttu-id="85efe-121">En el ejemplo siguiente se utiliza una referencia dinámica de pincel del sistema para establecer el fondo de un botón.</span><span class="sxs-lookup"><span data-stu-id="85efe-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="85efe-122">En el ejemplo siguiente se utiliza una referencia estática de pincel del sistema para establecer el fondo de un botón.</span><span class="sxs-lookup"><span data-stu-id="85efe-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="85efe-123">Para obtener un ejemplo que muestra cómo utilizar un color del sistema en un degradado, vea [usar colores del sistema en un degradado](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="85efe-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85efe-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="85efe-124">See also</span></span>
- [<span data-ttu-id="85efe-125">Usar colores del sistema en un degradado</span><span class="sxs-lookup"><span data-stu-id="85efe-125">Use System Colors in a Gradient</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)
- [<span data-ttu-id="85efe-126">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="85efe-126">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
