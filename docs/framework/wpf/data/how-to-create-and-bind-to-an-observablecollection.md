---
title: "C&#243;mo: Crear y enlazar a una colecci&#243;n ObservableCollection | Microsoft Docs"
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
  - "clases, ObservableCollection"
  - "enlace de datos, ObservableCollection (clase)"
  - "notificaciones"
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Crear y enlazar a una colecci&#243;n ObservableCollection
En este ejemplo se muestra cómo crear y enlazar una colección que se deriva de la clase <xref:System.Collections.ObjectModel.ObservableCollection%601>, que es una clase de colección que proporciona notificaciones cuando se agregan o quitan elementos.  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra la implementación de una colección `NameList`.  
  
 [!code-csharp[MultiBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[MultiBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameList.vb#1)]  
  
 Puede hacer que la colección esté disponible para enlazarla de la misma manera que con otros objetos de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], como se describe en [Hacer que los datos estén disponibles para el enlace en XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md).  Por ejemplo, puede crear instancias de la colección en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y especificar la colección como un recurso, como se muestra aquí:  
  
 [!code-xml[MultiBinding#OCHowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#ochowto)]  
[!code-xml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
  
 A continuación, puede enlazar la colección:  
  
 [!code-xml[MultiBinding#MultiBindingListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindinglistbox)]  
  
 La definición de `NameItemTemplate` no se muestra aquí.  
  
> [!NOTE]
>  Los objetos de la colección deben cumplir los requisitos descritos en [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md).  En particular, si utiliza <xref:System.Windows.Data.BindingMode> o <xref:System.Windows.Data.BindingMode> \(por ejemplo, si desea que la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se actualice cuando cambien dinámicamente las propiedades de origen\), debe implementar un mecanismo apropiado de notificación de cambio de propiedad, como la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Para obtener más información, consulte la sección Enlazar a colecciones en [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## Vea también  
 [Ordenar datos en una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Ordenar y agrupar datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)