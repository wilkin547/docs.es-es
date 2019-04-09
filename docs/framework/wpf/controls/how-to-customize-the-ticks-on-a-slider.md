---
title: Filtrar Personalizar las marcas de paso en un control Slider
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 3b32bbedb5f654ce75e90a827eb0c4dba1d4d345
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164247"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="30d9f-102">Filtrar Personalizar las marcas de paso en un control Slider</span><span class="sxs-lookup"><span data-stu-id="30d9f-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="30d9f-103">En este ejemplo se muestra cómo crear un <xref:System.Windows.Controls.Slider> control que contiene las marcas de graduación.</span><span class="sxs-lookup"><span data-stu-id="30d9f-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30d9f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30d9f-104">Example</span></span>  
 <span data-ttu-id="30d9f-105">El <xref:System.Windows.Controls.Primitives.TickBar> muestra cuando se establece la <xref:System.Windows.Controls.Slider.TickPlacement%2A> propiedad a un valor distinto de <xref:System.Windows.Controls.Primitives.TickPlacement.None>, que es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="30d9f-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="30d9f-106">El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.Slider> con un <xref:System.Windows.Controls.Primitives.TickBar> que muestra marcas de graduación.</span><span class="sxs-lookup"><span data-stu-id="30d9f-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="30d9f-107">El <xref:System.Windows.Controls.Slider.TickPlacement%2A> y <xref:System.Windows.Controls.Slider.TickFrequency%2A> propiedades definen la ubicación de las marcas de graduación y el intervalo entre ellos.</span><span class="sxs-lookup"><span data-stu-id="30d9f-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="30d9f-108">Al mover el <xref:System.Windows.Controls.Primitives.Thumb>, información sobre herramientas muestra el valor de la <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="30d9f-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="30d9f-109">El <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> propiedad define dónde se producen las informaciones sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="30d9f-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="30d9f-110">El <xref:System.Windows.Controls.Primitives.Thumb> movimientos corresponden a la ubicación de las marcas de graduación porque <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> está establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="30d9f-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="30d9f-111">El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.Slider.Ticks%2A> propiedad que se va a crear a lo largo de las marcas de graduación el <xref:System.Windows.Controls.Slider> a intervalos irregulares.</span><span class="sxs-lookup"><span data-stu-id="30d9f-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="30d9f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="30d9f-112">See also</span></span>

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [<span data-ttu-id="30d9f-113">Filtrar Enlazar un control deslizante con un valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="30d9f-113">How to: Bind a Slider to a Property Value</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))
