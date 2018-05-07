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
ms.openlocfilehash: d46a408bc1b5fc512905aa5bf176b13bd1511865
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Cómo: Buscar elementos generados por un objeto DataTemplate
Este ejemplo muestra cómo buscar elementos generados por un <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, hay un <xref:System.Windows.Controls.ListBox> que está enlazado a algunas [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos:  
  
 [!code-xaml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 El <xref:System.Windows.Controls.ListBox> usa las siguientes <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Si desea recuperar la <xref:System.Windows.Controls.TextBlock> elemento generado por la <xref:System.Windows.DataTemplate> de una determinada <xref:System.Windows.Controls.ListBoxItem>, tendrá que obtener el <xref:System.Windows.Controls.ListBoxItem>, buscar el <xref:System.Windows.Controls.ContentPresenter> dentro de ese <xref:System.Windows.Controls.ListBoxItem>y, a continuación, llame a <xref:System.Windows.FrameworkTemplate.FindName%2A> en el <xref:System.Windows.DataTemplate> que se establece en ese <xref:System.Windows.Controls.ContentPresenter>. En el ejemplo siguiente se muestra cómo realizar estos pasos. Con fines de demostración, este ejemplo crea un cuadro de mensaje que muestra el texto del contenido de la <xref:System.Windows.DataTemplate>-bloque de texto generado.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 La siguiente es la implementación de `FindVisualChild`, que usa el <xref:System.Windows.Media.VisualTreeHelper> métodos:  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Vea también  
 [Buscar elementos generados por un objeto ControlTemplate](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Ámbitos de nombres XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
