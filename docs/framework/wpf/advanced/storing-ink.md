---
title: "Almacenar entradas manuscritas | Microsoft Docs"
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
  - "Formato serializado de tinta (ISF)"
  - "entrada manuscrita, almacenar"
  - "ISF (Formato serializado de tinta)"
  - "recuperar la entrada manuscrita"
  - "almacenar la entrada manuscrita"
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Almacenar entradas manuscritas
Los métodos <xref:System.Windows.Ink.StrokeCollection.Save%2A> proporcionan compatibilidad para almacenar la entrada de lápiz como Formato serializado de tinta \(ISF\).  Los constructores de la clase <xref:System.Windows.Ink.StrokeCollection> proporcionan compatibilidad con la lectura de datos de entrada de lápiz.  
  
## Almacenar y recuperar entradas de lápiz  
 En esta sección se analiza la forma de almacenar y recuperar la entrada de lápiz en la plataforma [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 En el ejemplo siguiente se implementa un controlador de evento de clic de botón que muestra al usuario un cuadro de diálogo para guardar archivos y guarda la entrada de lápiz de un elemento <xref:System.Windows.Controls.InkCanvas> en un archivo.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 En el ejemplo siguiente se implementa un controlador de evento de clic de botón que muestra al usuario un cuadro de diálogo para abrir archivos y lee la entrada de lápiz del archivo en un elemento <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## Vea también  
 <xref:System.Windows.Controls.InkCanvas>   
 [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)