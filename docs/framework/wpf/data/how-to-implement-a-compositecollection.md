---
title: "C&#243;mo: Implementar una CompositeCollection | Microsoft Docs"
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
  - "clases, CompositeCollection"
  - "enlace de datos, CompositeCollection (clase)"
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Implementar una CompositeCollection
## Ejemplo  
 En el ejemplo siguiente se muestra cómo mostrar varias colecciones y elementos como una lista utilizando la clase <xref:System.Windows.Data.CompositeCollection>.  En este ejemplo, `GreekGods` es una colección <xref:System.Collections.ObjectModel.ObservableCollection%601> de objetos `GreekGod` personalizados.  Se definen plantillas de datos para que los objetos `GreekGod` y los objetos `GreekHero` aparezcan con un color de primer plano oro y cian, respectivamente.  
  
 [!code-xml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## Vea también  
 <xref:System.Windows.Data.CollectionContainer>   
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>   
 <xref:System.Windows.Data.XmlDataProvider>   
 <xref:System.Windows.DataTemplate>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)