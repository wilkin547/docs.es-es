---
title: 'Cómo: Establecer las propiedades de alto de un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124291"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="5da19-102">Cómo: Establecer las propiedades de alto de un elemento</span><span class="sxs-lookup"><span data-stu-id="5da19-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="5da19-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5da19-103">Example</span></span>  
 <span data-ttu-id="5da19-104">En este ejemplo se muestran visualmente las diferencias en el comportamiento de la representación entre las cuatro propiedades relacionadas con el alto en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5da19-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="5da19-105">La clase <xref:System.Windows.FrameworkElement> expone cuatro propiedades que describen las características de alto de un elemento.</span><span class="sxs-lookup"><span data-stu-id="5da19-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="5da19-106">Estas cuatro propiedades pueden entrar en conflicto y, cuando lo hacen, el valor que tiene prioridad se determina de la siguiente manera: el valor <xref:System.Windows.FrameworkElement.MinHeight%2A> tiene prioridad sobre el valor <xref:System.Windows.FrameworkElement.MaxHeight%2A>, que a su vez tiene prioridad sobre el valor de <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="5da19-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="5da19-107">Una cuarta propiedad, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, es de solo lectura y notifica el alto real tal y como lo determinan las interacciones con el proceso de diseño.</span><span class="sxs-lookup"><span data-stu-id="5da19-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="5da19-108">En los siguientes [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos se dibuja un elemento de <xref:System.Windows.Shapes.Rectangle> (`rect1`) como elemento secundario de <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="5da19-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="5da19-109">Puede cambiar las propiedades de alto de un <xref:System.Windows.Shapes.Rectangle> mediante una serie de elementos <xref:System.Windows.Controls.ListBox> que representan los valores de propiedad de <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>y <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="5da19-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="5da19-110">De esta manera, la prioridad de cada propiedad se muestra visualmente.</span><span class="sxs-lookup"><span data-stu-id="5da19-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="5da19-111">Los siguientes ejemplos de código subyacente controlan los eventos que genera el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.</span><span class="sxs-lookup"><span data-stu-id="5da19-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="5da19-112">Cada controlador toma la entrada del <xref:System.Windows.Controls.ListBox>, analiza el valor como un <xref:System.Double>y aplica el valor a la propiedad relacionada con el alto especificado.</span><span class="sxs-lookup"><span data-stu-id="5da19-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="5da19-113">Los valores de alto también se convierten en una cadena y se escriben en varios elementos <xref:System.Windows.Controls.TextBlock> (la definición de esos elementos no se muestra en el código XAML seleccionado).</span><span class="sxs-lookup"><span data-stu-id="5da19-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="5da19-114">Para obtener el ejemplo completo, vea [ejemplo de propiedades de alto](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).</span><span class="sxs-lookup"><span data-stu-id="5da19-114">For the complete sample, see [Height Properties Sample](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da19-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5da19-115">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="5da19-116">Establecer las propiedades de ancho de un elemento</span><span class="sxs-lookup"><span data-stu-id="5da19-116">Set the Width Properties of an Element</span></span>](how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="5da19-117">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="5da19-117">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="5da19-118">Ejemplo de propiedades de alto</span><span class="sxs-lookup"><span data-stu-id="5da19-118">Height Properties Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
