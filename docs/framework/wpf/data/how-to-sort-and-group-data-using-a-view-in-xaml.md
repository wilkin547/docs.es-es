---
title: "C&#243;mo: Ordenar y agrupar datos mediante una vista en XAML | Microsoft Docs"
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
  - "enlace de datos, agrupar datos en vistas en XAML"
  - "enlace de datos, ordenar datos en vistas en XAML"
  - "agrupar datos en vistas en XAML"
  - "ordenar datos en vistas en XAML"
  - "vistas, agrupar datos"
  - "vistas, ordenar datos"
  - "XAML, agrupar datos en vistas"
  - "XAML, ordenar datos en vistas"
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Ordenar y agrupar datos mediante una vista en XAML
En este ejemplo se muestra cómo crear una vista de una recolección de datos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Las vistas aportan las funcionalidades de agrupar, ordenar, filtrar y la noción de un elemento actual.  
  
## Ejemplo  
 En el ejemplo siguiente, se define el recurso estático denominado *places* como una colección de objetos *Place*, en la que cada objeto *Place* consta de un nombre de ciudad y su estado.  El prefijo *src* se asigna al espacio de nombres donde se define el origen de datos *Places*.  El prefijo *scm* se asigna a `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` y *dat* se asigna a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 En el ejemplo siguiente se crea una vista de la recolección de datos ordenada por el nombre de la ciudad y agrupada por el estado.  
  
 [!code-xml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 La vista puede ser entonces un origen de enlace, como en el ejemplo siguiente:  
  
 [!code-xml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Para los enlaces a datos XML definidos en un recurso <xref:System.Windows.Data.XmlDataProvider>, coloque el símbolo @ delante del nombre XML.  
  
 [!code-xml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## Vea también  
 <xref:System.Windows.Data.CollectionViewSource>   
 [Obtener la vista predeterminada de una recolección de datos](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)