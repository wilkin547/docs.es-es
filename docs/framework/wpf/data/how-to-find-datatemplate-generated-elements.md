---
title: Procedimiento Buscar elementos generados por una clase DataTemplate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: de5a4937feabdb4486d9dcf9d5e5bfddd2356690
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932774"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Procedimiento Buscar elementos generados por una clase DataTemplate
En este ejemplo se muestra cómo buscar elementos generados por un <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, hay un <xref:System.Windows.Controls.ListBox> que está enlazado a algunas [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 El <xref:System.Windows.Controls.ListBox> usa las siguientes <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Si desea recuperar la <xref:System.Windows.Controls.TextBlock> elemento generado por el <xref:System.Windows.DataTemplate> de una determinada <xref:System.Windows.Controls.ListBoxItem>, deberá obtener la <xref:System.Windows.Controls.ListBoxItem>, encontrar la <xref:System.Windows.Controls.ContentPresenter> dentro de ese <xref:System.Windows.Controls.ListBoxItem>y, a continuación, llame a <xref:System.Windows.FrameworkTemplate.FindName%2A> en el <xref:System.Windows.DataTemplate> que se establece en el que <xref:System.Windows.Controls.ContentPresenter>. El ejemplo siguiente muestra cómo realizar esos pasos. Para fines de demostración, este ejemplo crea un cuadro de mensaje que muestra el texto del contenido de la <xref:System.Windows.DataTemplate>-bloque de texto generado.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 La siguiente es la implementación de `FindVisualChild`, que usa el <xref:System.Windows.Media.VisualTreeHelper> métodos:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Buscar elementos generados por el objeto ControlTemplate](../controls/how-to-find-controltemplate-generated-elements.md)
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
- [Ámbitos de nombres XAML de WPF](../advanced/wpf-xaml-namescopes.md)
- [Árboles en WPF](../advanced/trees-in-wpf.md)
