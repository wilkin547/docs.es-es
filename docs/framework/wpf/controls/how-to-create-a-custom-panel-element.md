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
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799147"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="d4f26-102">Cómo: Crear un elemento de panel personalizado</span><span class="sxs-lookup"><span data-stu-id="d4f26-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="d4f26-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4f26-103">Example</span></span>  
 <span data-ttu-id="d4f26-104">En este ejemplo se muestra cómo invalidar el comportamiento de diseño predeterminado del elemento <xref:System.Windows.Controls.Panel> y crear elementos de diseño personalizados que se derivan de <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="d4f26-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="d4f26-105">En el ejemplo se define un elemento de <xref:System.Windows.Controls.Panel> personalizado simple denominado `PlotPanel`, que coloca los elementos secundarios de acuerdo con dos coordenadas x e y codificadas de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="d4f26-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="d4f26-106">En este ejemplo, `x` y `y` están establecidos en `50`; por lo tanto, todos los elementos secundarios se colocan en esa ubicación en los ejes x e y.</span><span class="sxs-lookup"><span data-stu-id="d4f26-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="d4f26-107">Para implementar los comportamientos de <xref:System.Windows.Controls.Panel> personalizados, en el ejemplo se usan los métodos <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4f26-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="d4f26-108">Cada método devuelve los datos <xref:System.Windows.Size> necesarios para colocar y representar los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="d4f26-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d4f26-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4f26-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="d4f26-110">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="d4f26-110">Panels Overview</span></span>](panels-overview.md)
