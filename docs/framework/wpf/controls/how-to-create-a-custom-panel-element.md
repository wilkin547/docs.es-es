---
title: 'Cómo: Crear un elemento de panel personalizado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: bca8900ccb3c31a78066a43709a5e9334bc09eab
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43776718"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="0ed3a-102">Cómo: Crear un elemento de panel personalizado</span><span class="sxs-lookup"><span data-stu-id="0ed3a-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="0ed3a-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ed3a-103">Example</span></span>  
 <span data-ttu-id="0ed3a-104">En este ejemplo se muestra cómo invalidar el comportamiento de diseño predeterminado de la <xref:System.Windows.Controls.Panel> elemento y crear elementos de diseño personalizado que se derivan <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="0ed3a-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="0ed3a-105">El ejemplo define un simple personalizado <xref:System.Windows.Controls.Panel> elemento llamado `PlotPanel`, que coloca los elementos secundarios según dos rígida-coordenadas x e y-.</span><span class="sxs-lookup"><span data-stu-id="0ed3a-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="0ed3a-106">En este ejemplo, `x` y `y` están establecidos en `50`; por lo tanto, todos los elementos secundarios se colocan en esa ubicación en la x e y ejes.</span><span class="sxs-lookup"><span data-stu-id="0ed3a-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="0ed3a-107">Para implementar personalizado <xref:System.Windows.Controls.Panel> comportamientos, el ejemplo utiliza la <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="0ed3a-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="0ed3a-108">Cada método devuelve el <xref:System.Windows.Size> datos necesarios para colocar y representar los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="0ed3a-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0ed3a-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ed3a-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="0ed3a-110">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="0ed3a-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="0ed3a-111">Crear un ejemplo de Panel de ajuste de contenido personalizado</span><span class="sxs-lookup"><span data-stu-id="0ed3a-111">Create a Custom Content-Wrapping Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159979)
