---
title: 'Cómo: Enlazar a una colección y mostrar información basada en la selección'
description: Siga este ejemplo para averiguar cómo enlazar a una colección y Mostrar información basada en la selección en el Windows Presentation Foundation (WPF).
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
ms.openlocfilehash: fb8757ee6818a2812308a0a132fa9d06951ad52e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619616"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Cómo: Enlazar a una colección y mostrar información basada en la selección
En un escenario simple de detalles maestros, tiene un enlace de datos <xref:System.Windows.Controls.ItemsControl> como <xref:System.Windows.Controls.ListBox> . En función de la selección del usuario, se muestra más información sobre el elemento seleccionado. En este ejemplo se muestra cómo implementar este escenario.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `People` es una <xref:System.Collections.ObjectModel.ObservableCollection%601> de `Person` las clases de. Esta `Person` clase contiene tres propiedades: `FirstName` , `LastName` y `HomeTown` , todas de tipo `string` .  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <xref:System.Windows.Controls.ContentControl>Utiliza lo siguiente <xref:System.Windows.DataTemplate> que define cómo se presenta la información de un `Person` :  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 A continuación se muestra una captura de pantalla de lo que produce el ejemplo. <xref:System.Windows.Controls.ContentControl>Muestra las otras propiedades de la persona seleccionada.  
  
 ![Enlace a una colección](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 Los dos aspectos que se deben tener en cuenta en este ejemplo son:  
  
1. <xref:System.Windows.Controls.ListBox>Y <xref:System.Windows.Controls.ContentControl> enlazan al mismo origen. <xref:System.Windows.Data.Binding.Path%2A>No se especifican las propiedades de ambos enlaces porque ambos controles se enlazan a todo el objeto de colección.  
  
2. Debe establecer la <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad en `true` para que funcione. Al establecer esta propiedad, se asegura de que el elemento seleccionado siempre se establece como <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> . Como alternativa, si <xref:System.Windows.Controls.ListBox> obtiene datos de una <xref:System.Windows.Data.CollectionViewSource> , sincroniza la selección y la moneda automáticamente.  
  
 Tenga en cuenta que la `Person` clase invalida el `ToString` método de la siguiente manera. De forma predeterminada, <xref:System.Windows.Controls.ListBox> llama a `ToString` y muestra una representación de cadena de cada objeto de la colección enlazada. Esa es la razón por la que cada `Person` aparece como un nombre en el <xref:System.Windows.Controls.ListBox> .  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Vea también

- [Usar el patrón principal-detalle con datos jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Usar el patrón principal-detalle con datos XML jerárquicos](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre plantillas de datos](data-templating-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
