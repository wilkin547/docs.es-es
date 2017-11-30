---
title: "Cómo: Enlazar a una colección y mostrar información basada en la selección"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e92621e7e62750ae5ad73158232ccdabfb22287a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Cómo: Enlazar a una colección y mostrar información basada en la selección
En un escenario principal-detalle simple, tiene un enlace de datos <xref:System.Windows.Controls.ItemsControl> como un <xref:System.Windows.Controls.ListBox>. En función de la selección del usuario, se muestra más información acerca del elemento seleccionado. Este ejemplo muestra cómo implementar este escenario.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `People` es un <xref:System.Collections.ObjectModel.ObservableCollection%601> de `Person` clases. Esto `Person` clase contiene tres propiedades: `FirstName`, `LastName`, y `HomeTown`, todos del tipo `string`.  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 El <xref:System.Windows.Controls.ContentControl> usa las siguientes <xref:System.Windows.DataTemplate> que define cómo la información de un `Person` se presenta:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 La siguiente es una captura de pantalla de lo que genera el ejemplo. La <xref:System.Windows.Controls.ContentControl> muestra las demás propiedades de la persona seleccionada.  
  
 ![Enlazar a una colección](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 Las dos cosas que se observan en este ejemplo son:  
  
1.  El <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ContentControl> enlazar al mismo origen. El <xref:System.Windows.Data.Binding.Path%2A> no se especificaron las propiedades de ambos enlaces porque ambos controles se enlazan con el objeto de colección completa.  
  
2.  Debe establecer el <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> propiedad `true` para que funcione. Al establecer esta propiedad se asegura de que el elemento seleccionado siempre se establece como el <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Como alternativa, si la <xref:System.Windows.Controls.ListBox> obtiene datos de un <xref:System.Windows.Data.CollectionViewSource>, sincroniza automáticamente selección y moneda.  
  
 Tenga en cuenta que la `Person` clase invalida la `ToString` método del siguiente modo. De forma predeterminada, el <xref:System.Windows.Controls.ListBox> llamadas `ToString` y muestra una representación de cadena de cada objeto en la colección enlazada. Por eso cada `Person` aparece como un nombre en el <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Vea también  
 [Usar el patrón principal-detalle con datos jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [Usar el patrón principal-detalle con datos XML jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
