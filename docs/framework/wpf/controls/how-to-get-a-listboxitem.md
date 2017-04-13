---
title: "C&#243;mo: Obtener un elemento ListBoxItem | Microsoft Docs"
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
  - "ListBox (controles), obtener ListBoxItem"
  - "ListBoxItem"
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Obtener un elemento ListBoxItem
Si necesita obtener un <xref:System.Windows.Controls.ListBoxItem> específico en un índice determinado en un <xref:System.Windows.Controls.ListBox>, puede utilizar un <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.ListBox> y sus elementos.  
  
 [!code-xml[ListBoxItems#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se muestra cómo recuperar el elemento especificando el índice del elemento en la propiedad <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> de <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
 [!code-csharp[ListBoxItems#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 Después de recuperar el elemento de cuadro de lista, puede mostrar el contenido del elemento, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[ListBoxItems#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]