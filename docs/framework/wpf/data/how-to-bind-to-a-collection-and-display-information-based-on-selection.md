---
title: Procedimiento Enlazar a una colección y mostrar información basada en la selección
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 549f4e7af1a9aa623c7f8ff12b528f771a8ff806
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504788"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Procedimiento Enlazar a una colección y mostrar información basada en la selección
En un escenario sencillo de maestro y detalles, tiene un enlace de datos <xref:System.Windows.Controls.ItemsControl> como un <xref:System.Windows.Controls.ListBox>. Según la selección del usuario, mostrar más información sobre el elemento seleccionado. En este ejemplo se muestra cómo implementar este escenario.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `People` es un <xref:System.Collections.ObjectModel.ObservableCollection%601> de `Person` clases. Esto `Person` clase contiene tres propiedades: `FirstName`, `LastName`, y `HomeTown`, todos del tipo `string`.  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 El <xref:System.Windows.Controls.ContentControl> usa las siguientes <xref:System.Windows.DataTemplate> que define cómo la información de un `Person` se presenta:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 La siguiente es una captura de pantalla de lo que genera el ejemplo. La <xref:System.Windows.Controls.ContentControl> muestra las demás propiedades de la persona seleccionada.  
  
 ![Enlazar a una colección](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 Las dos cosas a tener en cuenta en este ejemplo son:  
  
1.  El <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ContentControl> enlazar al mismo origen. El <xref:System.Windows.Data.Binding.Path%2A> no se especifican las propiedades de ambos enlaces porque ambos controles se enlazan al objeto de colección completa.  
  
2.  Debe establecer el <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad `true` para que funcione. Al establecer esta propiedad garantiza que siempre se establece el elemento seleccionado como el <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Como alternativa, si la <xref:System.Windows.Controls.ListBox> obtiene sus datos desde un <xref:System.Windows.Data.CollectionViewSource>, sincronización automáticamente selección y moneda.  
  
 Tenga en cuenta que el `Person` clase invalida el `ToString` método del siguiente modo. De forma predeterminada, el <xref:System.Windows.Controls.ListBox> llamadas `ToString` y muestra una representación de cadena de cada objeto en la colección enlazada. Por eso cada `Person` aparece como un nombre en el <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Vea también
- [Usar el patrón principal-detalle con datos jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Usar el patrón principal-detalle con datos XML jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
