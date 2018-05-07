---
title: 'Cómo: Enlazar datos a un InkCanvas'
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 4081ae7dd6854934804062cfce60d10106c1e1d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a>Cómo: Enlazar datos a un InkCanvas
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo enlazar la <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedad de un <xref:System.Windows.Controls.InkCanvas> a otro <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 En el ejemplo siguiente se muestra cómo enlazar el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedad a un origen de datos.  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 En el ejemplo siguiente se declara dos <xref:System.Windows.Controls.InkCanvas> objetos en XAML y establece el enlace de datos entre ellos y otros orígenes de datos.  La primera <xref:System.Windows.Controls.InkCanvas>, llamado `ic`, se enlaza a dos orígenes de datos.  El <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> y <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedades `ic` están enlazados a <xref:System.Windows.Controls.ListBox> objetos, que a su vez se enlazan a las matrices definidas en el código XAML.  El <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, y <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedades del segundo <xref:System.Windows.Controls.InkCanvas> están enlazados al primer <xref:System.Windows.Controls.InkCanvas>, `ic`.  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
