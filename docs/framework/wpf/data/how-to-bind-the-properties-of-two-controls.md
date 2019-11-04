---
title: 'Cómo: Enlazar las propiedades de dos controles'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459171"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="790af-102">Cómo: Enlazar las propiedades de dos controles</span><span class="sxs-lookup"><span data-stu-id="790af-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="790af-103">En este ejemplo se muestra cómo enlazar la propiedad de un control con instancias a otro utilizando la propiedad <xref:System.Windows.Data.Binding.ElementName%2A>.</span><span class="sxs-lookup"><span data-stu-id="790af-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="790af-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="790af-104">Example</span></span>  
 <span data-ttu-id="790af-105">En el ejemplo siguiente se muestra cómo enlazar la propiedad <xref:System.Windows.Controls.Panel.Background%2A> de una <xref:System.Windows.Controls.Canvas> a la <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="790af-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="790af-106">propiedad de un <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="790af-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="790af-107">Cuando se representa este ejemplo, tiene un aspecto similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="790af-107">When this example is rendered it looks like the following:</span></span>  
  
![Captura de pantalla que muestra un cuadro combinado con el valor verde seleccionado y un cuadrado verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="790af-109">La propiedad de destino de enlace (en este ejemplo, la propiedad <xref:System.Windows.Controls.Panel.Background%2A>) debe ser una propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="790af-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="790af-110">Para obtener más información, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="790af-110">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790af-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="790af-111">See also</span></span>

- [<span data-ttu-id="790af-112">Especificación del origen de enlace</span><span class="sxs-lookup"><span data-stu-id="790af-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="790af-113">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="790af-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
