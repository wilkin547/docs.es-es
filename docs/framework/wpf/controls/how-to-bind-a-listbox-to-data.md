---
title: "C&#243;mo: Enlazar a datos un control ListBox | Microsoft Docs"
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
  - "enlazar datos, al control ListBox"
  - "enlace de datos, ListBox (control)"
  - "ListBox (controles), enlazar datos a"
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Enlazar a datos un control ListBox
Un programador de aplicaciones puede crear controles <xref:System.Windows.Controls.ListBox> sin especificar el contenido de cada elemento <xref:System.Windows.Controls.ListBoxItem> de manera independiente.  Puede utilizar el enlace de datos para enlazar los datos a los elementos individuales.  
  
 En el ejemplo siguiente se muestra cómo crear un objeto <xref:System.Windows.Controls.ListBox> que rellena los elementos <xref:System.Windows.Controls.ListBoxItem> mediante un enlace de datos a un origen de datos denominado *Colors*.  En este caso, no es necesario utilizar etiquetas de <xref:System.Windows.Controls.ListBoxItem> para especificar el contenido de cada elemento.  
  
## Ejemplo  
 [!code-xml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## Vea también  
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.Controls.ListBoxItem>   
 [Controles](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)