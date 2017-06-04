---
title: "C&#243;mo: Enlazar a una colecci&#243;n y mostrar informaci&#243;n basada en la selecci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "enlace de datos, enlace a colecciones"
  - "enlace de datos, crear vistas de colecciones de datos"
  - "enlace de datos, seleccionar datos para vistas"
  - "colecciones de datos, seleccionar datos para vistas"
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Enlazar a una colecci&#243;n y mostrar informaci&#243;n basada en la selecci&#243;n
En un escenario principal\-detalle simple, hay un objeto <xref:System.Windows.Controls.ItemsControl> enlazado a datos, como un control <xref:System.Windows.Controls.ListBox>.  Basándose en la selección del usuario, se muestra más información sobre el elemento seleccionado.  En este ejemplo se muestra cómo implementar este escenario.  
  
## Ejemplo  
 En este ejemplo, `People` es una colección <xref:System.Collections.ObjectModel.ObservableCollection%601> de clases `Person`.  Esta clase `Person` contiene tres propiedades: `FirstName`, `LastName` y `HomeTown`, todas de tipo `string`.  
  
 [!code-xml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <xref:System.Windows.Controls.ContentControl> utiliza la plantilla de datos <xref:System.Windows.DataTemplate> siguiente, que define cómo se presenta la información de `Person`:  
  
 [!code-xml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 A continuación, se muestra una captura de pantalla de lo que el ejemplo genera.  <xref:System.Windows.Controls.ContentControl> muestra las demás propiedades de la persona seleccionada.  
  
 ![Enlace a una colección](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding\_CollectionBindingSample")  
  
 Los dos puntos importantes de este ejemplo son:  
  
1.  <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ContentControl> se enlazan al mismo origen.  No se especifican las propiedades <xref:System.Windows.Data.Binding.Path%2A> de ambos enlaces porque los dos controles se enlazan al objeto de colección completo.  
  
2.  Para que funcione, debe establecer la propiedad <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> en `true`.  Al establecer esta propiedad se garantiza que el elemento seleccionado se establezca siempre como <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.  Como alternativa, si el control <xref:System.Windows.Controls.ListBox> obtiene sus datos de un objeto <xref:System.Windows.Data.CollectionViewSource>, sincronizará automáticamente la selección y la actualización.  
  
 Observe que la clase `Person` invalida el método `ToString` la manera siguiente.  De manera predeterminada, <xref:System.Windows.Controls.ListBox> llama a `ToString` y muestra una representación de cadena de cada objeto en la colección enlazada.  Por ello, cada objeto `Person` aparece como un nombre en <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## Vea también  
 [Usar el patrón principal\-detalle con datos jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)   
 [Usar el patrón principal\-detalle con datos XML jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)