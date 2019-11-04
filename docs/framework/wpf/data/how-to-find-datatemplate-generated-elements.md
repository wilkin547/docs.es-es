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
ms.openlocfilehash: f9265e3f7b287e1e8c264e89325f7c9649eebe2c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459136"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Cómo: Buscar elementos generados por un objeto DataTemplate
En este ejemplo se muestra cómo buscar elementos generados por un <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, hay un <xref:System.Windows.Controls.ListBox> que está enlazado a algunos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 En el <xref:System.Windows.Controls.ListBox> se usa el <xref:System.Windows.DataTemplate>siguiente:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Si desea recuperar el elemento <xref:System.Windows.Controls.TextBlock> generado por el <xref:System.Windows.DataTemplate> de una <xref:System.Windows.Controls.ListBoxItem>determinada, necesita obtener el <xref:System.Windows.Controls.ListBoxItem>, buscar el <xref:System.Windows.Controls.ContentPresenter> en ese <xref:System.Windows.Controls.ListBoxItem>y, a continuación, llamar a <xref:System.Windows.FrameworkTemplate.FindName%2A> en el <xref:System.Windows.DataTemplate> que se establece en. <xref:System.Windows.Controls.ContentPresenter>. En el ejemplo siguiente se muestra cómo realizar estos pasos. Para fines de demostración, este ejemplo crea un cuadro de mensaje que muestra el contenido de texto del bloque de texto generado por <xref:System.Windows.DataTemplate>.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 La siguiente es la implementación de `FindVisualChild`, que usa los métodos de <xref:System.Windows.Media.VisualTreeHelper>:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Vea también

- [Buscar elementos generados por un objeto ControlTemplate](../controls/how-to-find-controltemplate-generated-elements.md)
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Ámbitos de nombres XAML de WPF](../advanced/wpf-xaml-namescopes.md)
- [Árboles en WPF](../advanced/trees-in-wpf.md)
