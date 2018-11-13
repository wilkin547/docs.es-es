---
title: Cómo crear un contol Grid complejo
description: Un ejemplo sobre cómo usar un control de cuadrícula para crear un diseño similar a un calendario mensual.
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: e2356113457e8c9a6737132e9779e49c05a23d77
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50743929"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="dcc34-103">Cómo crear un contol Grid complejo</span><span class="sxs-lookup"><span data-stu-id="dcc34-103">How to create a complex Grid</span></span>

<span data-ttu-id="dcc34-104">En este ejemplo se muestra cómo usar un <xref:System.Windows.Controls.Grid> control para crear un diseño similar a un calendario mensual.</span><span class="sxs-lookup"><span data-stu-id="dcc34-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="dcc34-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dcc34-105">Example</span></span>

<span data-ttu-id="dcc34-106">El ejemplo siguiente define ocho filas y ocho columnas mediante el <xref:System.Windows.Controls.RowDefinition> y <xref:System.Windows.Controls.ColumnDefinition> clases.</span><span class="sxs-lookup"><span data-stu-id="dcc34-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="dcc34-107">Usa el <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> y <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> adjunta propiedades, junto con <xref:System.Windows.Shapes.Rectangle> elementos, que rellenan el fondo de varias columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="dcc34-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="dcc34-108">Este diseño es posible porque puede existir más de un elemento en cada celda de un <xref:System.Windows.Controls.Grid>, una diferencia principal entre <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Documents.Table>.</span><span class="sxs-lookup"><span data-stu-id="dcc34-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="dcc34-109">En el ejemplo se utiliza degradados verticales para <xref:System.Windows.Shapes.Shape.Fill%2A> las columnas y filas para mejorar la presentación visual y la legibilidad del calendario.</span><span class="sxs-lookup"><span data-stu-id="dcc34-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="dcc34-110">Estilo <xref:System.Windows.Controls.TextBlock> elementos representan las fechas y los días de la semana.</span><span class="sxs-lookup"><span data-stu-id="dcc34-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="dcc34-111"><xref:System.Windows.Controls.TextBlock> los elementos tienen una posición absoluta dentro de sus celdas mediante el uso de la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad y las propiedades de alineación que se definen dentro del estilo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dcc34-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="dcc34-112">La siguiente imagen muestra el control resultante, un calendario personalizable:</span><span class="sxs-lookup"><span data-stu-id="dcc34-112">The following image shows the resulting control, a customizable calendar:</span></span>

![Captura de pantalla del control resultante](./media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="dcc34-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcc34-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="dcc34-115">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="dcc34-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="dcc34-116">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="dcc34-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="dcc34-117">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="dcc34-117">Table Overview</span></span>](../advanced/table-overview.md)