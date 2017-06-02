---
title: "C&#243;mo: Buscar el elemento de origen en un controlador de eventos | Microsoft Docs"
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
  - "controladores de eventos, buscar elemento de origen en"
  - "elemento de origen en controladores de eventos"
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Buscar el elemento de origen en un controlador de eventos
En este ejemplo se muestra cómo buscar el elemento de origen en un controlador de eventos.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> que se declara en un archivo de código subyacente.  Cuando un usuario hace clic en el botón al que el controlador está asociado, el controlador cambia el valor de una propiedad.  El código del controlador utiliza la propiedad <xref:System.Windows.RoutedEventArgs.Source%2A> de los datos del evento enrutado que se comunican en los argumentos de evento para cambiar el valor de propiedad <xref:System.Windows.FrameworkElement.Width%2A> del elemento <xref:System.Windows.RoutedEventArgs.Source%2A>.  
  
 [!code-xml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## Vea también  
 <xref:System.Windows.RoutedEventArgs>   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)