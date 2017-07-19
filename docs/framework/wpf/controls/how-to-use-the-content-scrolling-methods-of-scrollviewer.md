---
title: "C&#243;mo: Utilizar los m&#233;todos de desplazamiento de contenido de ScrollViewer | Microsoft Docs"
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
  - "IScrollInfo (interfaz)"
  - "métodos de desplazamiento"
  - "ScrollViewer (control), métodos de desplazamiento"
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Utilizar los m&#233;todos de desplazamiento de contenido de ScrollViewer
En este ejemplo se muestra cómo utilizar los métodos de desplazamiento del elemento <xref:System.Windows.Controls.ScrollViewer>.  Estos métodos proporcionan desplazamiento incremental del contenido, ya sea por líneas o por páginas, en <xref:System.Windows.Controls.ScrollViewer>.  
  
## Ejemplo  
 En el ejemplo siguiente se un control crea <xref:System.Windows.Controls.ScrollViewer> denominado `sv1`, que hospeda un elemento secundario <xref:System.Windows.Controls.TextBlock>.  Dado que <xref:System.Windows.Controls.TextBlock> es mayor que el elemento primario <xref:System.Windows.Controls.ScrollViewer>, aparecen barras de desplazamiento para habilitar el desplazamiento.  Los elementos <xref:System.Windows.Controls.Button> que representan los diversos métodos del desplazamiento se acoplan a la izquierda en un control <xref:System.Windows.Controls.StackPanel> independiente.  Cada objeto <xref:System.Windows.Controls.Button> del archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] llama a un método personalizado relacionado que controla el comportamiento del desplazamiento en <xref:System.Windows.Controls.ScrollViewer>.  
  
 [!code-xml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se utilizan los métodos <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> y <xref:System.Windows.Controls.ScrollViewer.LineDown%2A>.  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## Vea también  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.StackPanel>