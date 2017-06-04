---
title: "C&#243;mo: Girar entrada manuscrita | Microsoft Docs"
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
  - "entrada manuscrita, rotar"
  - "girar la entrada manuscrita"
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Girar entrada manuscrita
## Ejemplo  
 En el ejemplo siguiente se copia la entrada de lápiz de un objeto <xref:System.Windows.Controls.InkCanvas> en un objeto <xref:System.Windows.Controls.Canvas> que contiene un objeto <xref:System.Windows.Controls.InkPresenter>.  Cuando la aplicación copia la entrada de lápiz, también la gira en el sentido de las agujas del reloj 90 grados.  
  
 [!code-xml[HowToRotateInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## Ejemplo  
 El ejemplo siguiente es un objeto <xref:System.Windows.Documents.Adorner> personalizado que gira los trazos en un objeto <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[AdornerForStrokes#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 En el ejemplo siguiente se es un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que define un objeto <xref:System.Windows.Controls.InkPresenter> y lo rellena con entrada de lápiz.  El controlador de eventos `Window_Loaded` agrega el adorno personalizado al objeto <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-xml[AdornerForStrokes#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]