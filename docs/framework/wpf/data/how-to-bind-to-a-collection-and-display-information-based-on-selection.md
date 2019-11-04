---
title: 'Cómo: Enlazar a una colección y mostrar información basada en la selección'
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
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459144"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Cómo: Enlazar a una colección y mostrar información basada en la selección
En un escenario de detalles maestros sencillo, tiene un <xref:System.Windows.Controls.ItemsControl> enlazado a datos, como un <xref:System.Windows.Controls.ListBox>. En función de la selección del usuario, se muestra más información sobre el elemento seleccionado. En este ejemplo se muestra cómo implementar este escenario.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `People` es una <xref:System.Collections.ObjectModel.ObservableCollection%601> de clases `Person`. Esta `Person` clase contiene tres propiedades: `FirstName`, `LastName`y `HomeTown`, todo tipo `string`.  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 En el <xref:System.Windows.Controls.ContentControl> se usa el <xref:System.Windows.DataTemplate> siguiente que define cómo se presenta la información de un `Person`:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 A continuación se muestra una captura de pantalla de lo que produce el ejemplo. En el <xref:System.Windows.Controls.ContentControl> se muestran las demás propiedades de la persona seleccionada.  
  
 ![Enlazar a una colección](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 Los dos aspectos que se deben tener en cuenta en este ejemplo son:  
  
1. El <xref:System.Windows.Controls.ListBox> y el <xref:System.Windows.Controls.ContentControl> enlazan al mismo origen. No se especifican las propiedades <xref:System.Windows.Data.Binding.Path%2A> de ambos enlaces porque ambos controles se enlazan a todo el objeto de colección.  
  
2. Debe establecer la propiedad <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> en `true` para que funcione. Al establecer esta propiedad, se asegura de que el elemento seleccionado siempre se establece como <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Como alternativa, si el <xref:System.Windows.Controls.ListBox> obtiene datos de una <xref:System.Windows.Data.CollectionViewSource>, sincroniza la selección y la moneda automáticamente.  
  
 Tenga en cuenta que la clase `Person` invalida el método `ToString` de la siguiente manera. De forma predeterminada, el <xref:System.Windows.Controls.ListBox> llama a `ToString` y muestra una representación de cadena de cada objeto de la colección enlazada. Esa es la razón por la que cada `Person` aparece como nombre en el <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Vea también

- [Usar el patrón principal-detalle con datos jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Usar el patrón principal-detalle con datos XML jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre plantillas de datos](data-templating-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
