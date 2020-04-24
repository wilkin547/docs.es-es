---
title: 'Cómo: Buscar elementos generados por un objeto DataTemplate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: 3b222880aa4eda32502e3dcece2fa5c0b57b7a51
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646432"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Cómo: Buscar elementos generados por un objeto DataTemplate
En este ejemplo se muestra cómo buscar <xref:System.Windows.DataTemplate>elementos generados por un archivo .  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, <xref:System.Windows.Controls.ListBox> hay un que está enlazado a algunos datos XML:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Los <xref:System.Windows.Controls.ListBox> siguientes <xref:System.Windows.DataTemplate>utiliza:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Si desea recuperar <xref:System.Windows.Controls.TextBlock> el elemento generado <xref:System.Windows.DataTemplate> por <xref:System.Windows.Controls.ListBoxItem>el de un <xref:System.Windows.Controls.ListBoxItem>determinado , <xref:System.Windows.Controls.ContentPresenter> debe <xref:System.Windows.Controls.ListBoxItem>obtener el <xref:System.Windows.FrameworkTemplate.FindName%2A> , <xref:System.Windows.DataTemplate> buscar el <xref:System.Windows.Controls.ContentPresenter>dentro de ese , y, a continuación, llamar a la que se establece en ese . En el ejemplo siguiente se muestra cómo realizar esos pasos. Para fines de demostración, en este ejemplo se <xref:System.Windows.DataTemplate>crea un cuadro de mensaje que muestra el contenido de texto del bloque de texto generado.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 A continuación se `FindVisualChild`muestra la <xref:System.Windows.Media.VisualTreeHelper> implementación de , que utiliza los métodos:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Consulte también

- [Procedimiento para buscar elementos generados por un objeto ControlTemplate](../controls/how-to-find-controltemplate-generated-elements.md)
- [Descripción general del enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas de procedimientos](data-binding-how-to-topics.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Ámbitos de nombres XAML de WPF](../advanced/wpf-xaml-namescopes.md)
- [Árboles en WPF](../advanced/trees-in-wpf.md)
