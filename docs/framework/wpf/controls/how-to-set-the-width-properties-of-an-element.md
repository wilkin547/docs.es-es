---
title: Filtrar Establecer las propiedades de ancho de un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: a8fdc7c6659eb33f948741145c0b2e100bb133e4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376850"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="83020-102">Filtrar Establecer las propiedades de ancho de un elemento</span><span class="sxs-lookup"><span data-stu-id="83020-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="83020-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83020-103">Example</span></span>  
 <span data-ttu-id="83020-104">Este ejemplo muestran las diferencias de comportamiento entre las cuatro propiedades de ancho en representación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83020-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="83020-105">La <xref:System.Windows.FrameworkElement> clase expone cuatro propiedades que describen las características de ancho de un elemento.</span><span class="sxs-lookup"><span data-stu-id="83020-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="83020-106">Estas cuatro propiedades pueden entrar en conflicto y, cuando lo hacen, el valor que tiene prioridad se determina como sigue: el <xref:System.Windows.FrameworkElement.MinWidth%2A> valor tiene prioridad sobre la <xref:System.Windows.FrameworkElement.MaxWidth%2A> valor, que a su vez tiene prioridad sobre la <xref:System.Windows.FrameworkElement.Width%2A> valor.</span><span class="sxs-lookup"><span data-stu-id="83020-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="83020-107">Una propiedad de la cuarta, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, es de solo lectura y notifica el ancho real determinado por las interacciones con el proceso de diseño.</span><span class="sxs-lookup"><span data-stu-id="83020-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="83020-108">La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos dibujar un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) como un elemento secundario de <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="83020-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="83020-109">Puede cambiar las propiedades de ancho de un <xref:System.Windows.Shapes.Rectangle> mediante el uso de una serie de <xref:System.Windows.Controls.ListBox> elementos que representan los valores de propiedad <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, y <xref:System.Windows.FrameworkElement.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="83020-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="83020-110">De esta manera, se muestra gráficamente la prioridad de cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="83020-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="83020-111">Los siguientes ejemplos de código subyacente controlan los eventos que el <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="83020-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="83020-112">Cada método personalizado toma la entrada de la <xref:System.Windows.Controls.ListBox>, analiza el valor como un <xref:System.Double>y se aplica el valor a la propiedad relacionada con el ancho especificada.</span><span class="sxs-lookup"><span data-stu-id="83020-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="83020-113">Los valores de ancho también se convierte en una cadena y escritos en varios <xref:System.Windows.Controls.TextBlock> elementos (definición de esos elementos no se muestra en el XAML seleccionado).</span><span class="sxs-lookup"><span data-stu-id="83020-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="83020-114">Para obtener un ejemplo completo, vea [ejemplo de comparación de las propiedades ancho](https://go.microsoft.com/fwlink/?LinkID=160050).</span><span class="sxs-lookup"><span data-stu-id="83020-114">For the complete sample, see [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83020-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="83020-115">See also</span></span>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [<span data-ttu-id="83020-116">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="83020-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="83020-117">Establecer las propiedades de alto de un elemento</span><span class="sxs-lookup"><span data-stu-id="83020-117">Set the Height Properties of an Element</span></span>](how-to-set-the-height-properties-of-an-element.md)
- [<span data-ttu-id="83020-118">Ejemplo de comparación de las propiedades de ancho</span><span class="sxs-lookup"><span data-stu-id="83020-118">Width Properties Comparison Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160050)
