---
title: 'Cómo: Crear un contol Grid complejo'
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: 49bf9781d56b93fd4529f3c9b62deb171e69155f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553600"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="b806b-102">Cómo: Crear un contol Grid complejo</span><span class="sxs-lookup"><span data-stu-id="b806b-102">How to: Create a Complex Grid</span></span>
<span data-ttu-id="b806b-103">Este ejemplo muestra cómo utilizar un <xref:System.Windows.Controls.Grid> para crear el diseño que parezca un calendario mensual.</span><span class="sxs-lookup"><span data-stu-id="b806b-103">This example shows how to use a <xref:System.Windows.Controls.Grid> to create layout that looks like a monthly calendar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b806b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b806b-104">Example</span></span>  
 <span data-ttu-id="b806b-105">En el ejemplo siguiente se define ocho filas y ocho columnas mediante el <xref:System.Windows.Controls.RowDefinition> y <xref:System.Windows.Controls.ColumnDefinition> clases.</span><span class="sxs-lookup"><span data-stu-id="b806b-105">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="b806b-106">Usa el <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> y <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> adjunta propiedades, junto con <xref:System.Windows.Shapes.Rectangle> elementos, que llenan los fondos de varias columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="b806b-106">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="b806b-107">Este diseño es posible porque puede existir más de un elemento en cada celda de un <xref:System.Windows.Controls.Grid>, una diferencia principal entre <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Documents.Table>.</span><span class="sxs-lookup"><span data-stu-id="b806b-107">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>  
  
 <span data-ttu-id="b806b-108">En el ejemplo se utiliza degradados verticales para <xref:System.Windows.Shapes.Shape.Fill%2A> las columnas y filas con el fin de mejorar la presentación visual y mejorar la legibilidad del calendario.</span><span class="sxs-lookup"><span data-stu-id="b806b-108">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows in order to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="b806b-109">Un estilo <xref:System.Windows.Controls.TextBlock> elementos representan las fechas y los días de la semana.</span><span class="sxs-lookup"><span data-stu-id="b806b-109">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="b806b-110"><xref:System.Windows.Controls.TextBlock> elementos tienen una posición absoluta dentro de sus celdas usando la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad y las propiedades de alineación que se definen en el estilo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b806b-110"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b806b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b806b-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [<span data-ttu-id="b806b-112">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="b806b-112">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="b806b-113">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="b806b-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="b806b-114">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="b806b-114">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
