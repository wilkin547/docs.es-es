---
title: 'Cómo: Establecer las propiedades de ancho de un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 682929625612114d042e4619d8388617988b3c48
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124278"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="c5e85-102">Cómo: Establecer las propiedades de ancho de un elemento</span><span class="sxs-lookup"><span data-stu-id="c5e85-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="c5e85-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5e85-103">Example</span></span>  
 <span data-ttu-id="c5e85-104">En este ejemplo se muestran visualmente las diferencias en el comportamiento de la representación entre las cuatro propiedades relacionadas con el ancho en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5e85-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="c5e85-105">La clase <xref:System.Windows.FrameworkElement> expone cuatro propiedades que describen las características de ancho de un elemento.</span><span class="sxs-lookup"><span data-stu-id="c5e85-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="c5e85-106">Estas cuatro propiedades pueden entrar en conflicto y, cuando lo hacen, el valor que tiene prioridad se determina de la siguiente manera: el valor <xref:System.Windows.FrameworkElement.MinWidth%2A> tiene prioridad sobre el valor <xref:System.Windows.FrameworkElement.MaxWidth%2A>, que a su vez tiene prioridad sobre el valor de <xref:System.Windows.FrameworkElement.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5e85-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="c5e85-107">Una cuarta propiedad, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, es de solo lectura y notifica el ancho real según lo establecido por las interacciones con el proceso de diseño.</span><span class="sxs-lookup"><span data-stu-id="c5e85-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="c5e85-108">En los siguientes [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos se dibuja un elemento de <xref:System.Windows.Shapes.Rectangle> (`rect1`) como elemento secundario de <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="c5e85-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="c5e85-109">Puede cambiar las propiedades de ancho de un <xref:System.Windows.Shapes.Rectangle> mediante una serie de elementos <xref:System.Windows.Controls.ListBox> que representan los valores de propiedad de <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>y <xref:System.Windows.FrameworkElement.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5e85-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="c5e85-110">De esta manera, la prioridad de cada propiedad se muestra visualmente.</span><span class="sxs-lookup"><span data-stu-id="c5e85-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="c5e85-111">Los siguientes ejemplos de código subyacente controlan los eventos que genera el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.</span><span class="sxs-lookup"><span data-stu-id="c5e85-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="c5e85-112">Cada método personalizado toma la entrada del <xref:System.Windows.Controls.ListBox>, analiza el valor como un <xref:System.Double>y aplica el valor a la propiedad relacionada con el ancho especificada.</span><span class="sxs-lookup"><span data-stu-id="c5e85-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="c5e85-113">Los valores de ancho también se convierten en una cadena y se escriben en varios elementos <xref:System.Windows.Controls.TextBlock> (la definición de esos elementos no se muestra en el código XAML seleccionado).</span><span class="sxs-lookup"><span data-stu-id="c5e85-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="c5e85-114">Para obtener el ejemplo completo, vea [ejemplo de comparación de propiedades de ancho](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).</span><span class="sxs-lookup"><span data-stu-id="c5e85-114">For the complete sample, see [Width Properties Comparison Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e85-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5e85-115">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [<span data-ttu-id="c5e85-116">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="c5e85-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="c5e85-117">Establecer las propiedades de alto de un elemento</span><span class="sxs-lookup"><span data-stu-id="c5e85-117">Set the Height Properties of an Element</span></span>](how-to-set-the-height-properties-of-an-element.md)
- [<span data-ttu-id="c5e85-118">Ejemplo de comparación de propiedades de ancho</span><span class="sxs-lookup"><span data-stu-id="c5e85-118">Width Properties Comparison Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)
