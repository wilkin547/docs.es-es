---
title: Filtrar Establecer las propiedades de alto de un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: fb655630336c3b69afdc726a2e3c5a2cb8838667
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221592"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="2b153-102">Filtrar Establecer las propiedades de alto de un elemento</span><span class="sxs-lookup"><span data-stu-id="2b153-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="2b153-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b153-103">Example</span></span>  
 <span data-ttu-id="2b153-104">Este ejemplo muestran las diferencias de comportamiento entre las cuatro propiedades de altura en representación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b153-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="2b153-105">La <xref:System.Windows.FrameworkElement> clase expone cuatro propiedades que describen las características de alto de un elemento.</span><span class="sxs-lookup"><span data-stu-id="2b153-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="2b153-106">Estas cuatro propiedades pueden entrar en conflicto y, cuando lo hacen, el valor que tiene prioridad se determina como sigue: el <xref:System.Windows.FrameworkElement.MinHeight%2A> valor tiene prioridad sobre la <xref:System.Windows.FrameworkElement.MaxHeight%2A> valor, que a su vez tiene prioridad sobre la <xref:System.Windows.FrameworkElement.Height%2A> valor.</span><span class="sxs-lookup"><span data-stu-id="2b153-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="2b153-107">Una propiedad de la cuarta, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, es de solo lectura y notifica el alto real determinado por las interacciones con el proceso de diseño.</span><span class="sxs-lookup"><span data-stu-id="2b153-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="2b153-108">La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos dibujar un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) como un elemento secundario de <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="2b153-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="2b153-109">Puede cambiar las propiedades de alto de un <xref:System.Windows.Shapes.Rectangle> mediante el uso de una serie de <xref:System.Windows.Controls.ListBox> elementos que representan los valores de propiedad <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, y <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b153-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="2b153-110">De esta manera, se muestra gráficamente la prioridad de cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b153-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="2b153-111">Los siguientes ejemplos de código subyacente controlan los eventos que el <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="2b153-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="2b153-112">Cada controlador toma la entrada de la <xref:System.Windows.Controls.ListBox>, analiza el valor como un <xref:System.Double>y se aplica el valor a la propiedad relacionada con el alto especificada.</span><span class="sxs-lookup"><span data-stu-id="2b153-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="2b153-113">Los valores alto también se convierten en una cadena y escritos en varios <xref:System.Windows.Controls.TextBlock> elementos (definición de esos elementos no se muestra en el XAML seleccionado).</span><span class="sxs-lookup"><span data-stu-id="2b153-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="2b153-114">Para obtener un ejemplo completo, vea [alto propiedades ejemplo](https://go.microsoft.com/fwlink/?LinkID=159993).</span><span class="sxs-lookup"><span data-stu-id="2b153-114">For the complete sample, see [Height Properties Sample](https://go.microsoft.com/fwlink/?LinkID=159993).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b153-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b153-115">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="2b153-116">Establecer las propiedades de ancho de un elemento</span><span class="sxs-lookup"><span data-stu-id="2b153-116">Set the Width Properties of an Element</span></span>](how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="2b153-117">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="2b153-117">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="2b153-118">Ejemplo de propiedades de alto</span><span class="sxs-lookup"><span data-stu-id="2b153-118">Height Properties Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159993)
