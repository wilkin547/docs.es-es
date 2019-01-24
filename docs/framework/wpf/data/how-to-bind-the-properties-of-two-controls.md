---
title: Procedimiento Enlazar las propiedades de dos controles
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 63584872c027ed3a80698304a7221c161c8d928a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570257"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="b4d3f-102">Procedimiento Enlazar las propiedades de dos controles</span><span class="sxs-lookup"><span data-stu-id="b4d3f-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="b4d3f-103">En este ejemplo se muestra cómo enlazar la propiedad de un control con instancias a la de otra mediante el <xref:System.Windows.Data.Binding.ElementName%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b4d3f-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4d3f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b4d3f-104">Example</span></span>  
 <span data-ttu-id="b4d3f-105">El ejemplo siguiente muestra cómo enlazar la <xref:System.Windows.Controls.Panel.Background%2A> propiedad de un <xref:System.Windows.Controls.Canvas> a la <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="b4d3f-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="b4d3f-106">propiedad de un <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="b4d3f-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="b4d3f-107">Cuando se representa este ejemplo, tiene un aspecto similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4d3f-107">When this example is rendered it looks like the following:</span></span>  
  
 <span data-ttu-id="b4d3f-108">![Un lienzo con un fondo verde](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span><span class="sxs-lookup"><span data-stu-id="b4d3f-108">![A canvas with a green background](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span></span>  
  
 <span data-ttu-id="b4d3f-109">**Tenga en cuenta** la propiedad de destino de enlace (en este ejemplo, el <xref:System.Windows.Controls.Panel.Background%2A> propiedad) debe ser una propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="b4d3f-109">**Note** The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="b4d3f-110">Para obtener más información, consulte [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b4d3f-110">For more information, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d3f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4d3f-111">See also</span></span>
- [<span data-ttu-id="b4d3f-112">Especificación del origen de enlace</span><span class="sxs-lookup"><span data-stu-id="b4d3f-112">Specify the Binding Source</span></span>](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)
- [<span data-ttu-id="b4d3f-113">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="b4d3f-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
