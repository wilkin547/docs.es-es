---
title: "Cómo: Crear un contol Grid complejo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9dfb913407622f3cbd9a067a94cc6400b501e2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-complex-grid"></a>Cómo: Crear un contol Grid complejo
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Controls.Grid> para crear el diseño que parezca un calendario mensual.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define ocho filas y ocho columnas mediante el <xref:System.Windows.Controls.RowDefinition> y <xref:System.Windows.Controls.ColumnDefinition> clases. Usa el <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> y <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> adjunta propiedades, junto con <xref:System.Windows.Shapes.Rectangle> elementos, que llenan los fondos de varias columnas y filas. Este diseño es posible porque puede existir más de un elemento en cada celda de un <xref:System.Windows.Controls.Grid>, una diferencia principal entre <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Documents.Table>.  
  
 En el ejemplo se utiliza degradados verticales para <xref:System.Windows.Shapes.Shape.Fill%2A> las columnas y filas con el fin de mejorar la presentación visual y mejorar la legibilidad del calendario. Un estilo <xref:System.Windows.Controls.TextBlock> elementos representan las fechas y los días de la semana. <xref:System.Windows.Controls.TextBlock>elementos tienen una posición absoluta dentro de sus celdas usando la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad y las propiedades de alineación que se definen en el estilo de la aplicación.  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md)
