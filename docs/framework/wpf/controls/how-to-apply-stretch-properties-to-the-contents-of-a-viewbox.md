---
title: Procedimiento Aplicar propiedades de expansión al contenido de un Viewbox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: 08358ea07e0c41e3b7cdf52251a3ed4296035e2d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209884"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a>Procedimiento Aplicar propiedades de expansión al contenido de un Viewbox
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo cambiar el valor de la <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> y <xref:System.Windows.Controls.Viewbox.Stretch%2A> las propiedades de un <xref:System.Windows.Controls.Viewbox>.  
  
 El primer ejemplo utiliza [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un <xref:System.Windows.Controls.Viewbox> elemento. Asigna un <xref:System.Windows.FrameworkElement.MaxWidth%2A> y <xref:System.Windows.FrameworkElement.MaxHeight%2A> de 400. El ejemplo anida un <xref:System.Windows.Controls.Image> elemento dentro de la <xref:System.Windows.Controls.Viewbox>. <xref:System.Windows.Controls.Button> elementos que corresponden a los valores de propiedad para el <xref:System.Windows.Controls.Viewbox.Stretch%2A> y <xref:System.Windows.Controls.StretchDirection> enumeraciones manipulan el comportamiento de ajuste de anidado <xref:System.Windows.Controls.Image>.  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 Los siguientes identificadores de archivo de código subyacente del <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos que el anterior [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en el ejemplo se define.  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Viewbox>
- <xref:System.Windows.Media.Stretch>
- <xref:System.Windows.Controls.StretchDirection>
