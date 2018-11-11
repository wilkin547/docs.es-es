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
# <a name="how-to-create-a-complex-grid"></a>Cómo crear un contol Grid complejo

En este ejemplo se muestra cómo usar un <xref:System.Windows.Controls.Grid> control para crear un diseño similar a un calendario mensual.

## <a name="example"></a>Ejemplo

El ejemplo siguiente define ocho filas y ocho columnas mediante el <xref:System.Windows.Controls.RowDefinition> y <xref:System.Windows.Controls.ColumnDefinition> clases. Usa el <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> y <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> adjunta propiedades, junto con <xref:System.Windows.Shapes.Rectangle> elementos, que rellenan el fondo de varias columnas y filas. Este diseño es posible porque puede existir más de un elemento en cada celda de un <xref:System.Windows.Controls.Grid>, una diferencia principal entre <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Documents.Table>.

En el ejemplo se utiliza degradados verticales para <xref:System.Windows.Shapes.Shape.Fill%2A> las columnas y filas para mejorar la presentación visual y la legibilidad del calendario. Estilo <xref:System.Windows.Controls.TextBlock> elementos representan las fechas y los días de la semana. <xref:System.Windows.Controls.TextBlock> los elementos tienen una posición absoluta dentro de sus celdas mediante el uso de la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad y las propiedades de alineación que se definen dentro del estilo de la aplicación.

[!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

La siguiente imagen muestra el control resultante, un calendario personalizable:

![Captura de pantalla del control resultante](./media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [Información general sobre el dibujo con colores sólidos y degradados](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Información general sobre elementos Panel](panels-overview.md)
- [Información general sobre tablas](../advanced/table-overview.md)