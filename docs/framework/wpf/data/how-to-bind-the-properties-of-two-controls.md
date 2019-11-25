---
title: 'Cómo: Enlazar las propiedades de dos controles'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: d38c473b8c4d3f71f1e3decd4f66be248665c57b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974815"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="42b3f-102">Cómo: Enlazar las propiedades de dos controles</span><span class="sxs-lookup"><span data-stu-id="42b3f-102">How to: Bind the Properties of Two Controls</span></span>

<span data-ttu-id="42b3f-103">En este ejemplo se muestra cómo enlazar la propiedad de un control con instancias a otro utilizando la propiedad <xref:System.Windows.Data.Binding.ElementName%2A>.</span><span class="sxs-lookup"><span data-stu-id="42b3f-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="42b3f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42b3f-104">Example</span></span>

<span data-ttu-id="42b3f-105">En el ejemplo siguiente se muestra cómo enlazar la propiedad <xref:System.Windows.Controls.Panel.Background%2A> de una <xref:System.Windows.Controls.Canvas> a la propiedad [SelectedItem. Content](xref:System.Windows.Controls.ContentControl.Content%2A) de un <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="42b3f-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the [SelectedItem.Content](xref:System.Windows.Controls.ContentControl.Content%2A) property of a <xref:System.Windows.Controls.ComboBox>:</span></span>

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

<span data-ttu-id="42b3f-106">Cuando se representa este ejemplo, tiene un aspecto similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42b3f-106">When this example is rendered it looks like the following:</span></span>

![Captura de pantalla que muestra un cuadro combinado con el valor verde seleccionado y un cuadrado verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="42b3f-108">La propiedad de destino de enlace (en este ejemplo, la propiedad <xref:System.Windows.Controls.Panel.Background%2A>) debe ser una propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="42b3f-108">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="42b3f-109">Para obtener más información, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="42b3f-109">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="42b3f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="42b3f-110">See also</span></span>

- [<span data-ttu-id="42b3f-111">Especificación del origen de enlace</span><span class="sxs-lookup"><span data-stu-id="42b3f-111">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="42b3f-112">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="42b3f-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
