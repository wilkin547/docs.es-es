---
title: "Reconocimiento de entradas manuscritas | Microsoft Docs"
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
  - "reconocimiento de escritura a mano"
  - "reconocer escritura a mano"
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Reconocimiento de entradas manuscritas
En esta sección se tratan los principios de reconocimiento relativos a la entrada de lápiz digital en la plataforma [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## Soluciones de reconocimiento  
 En el ejemplo siguiente se muestra cómo reconocer la entrada de lápiz usando <xref:System.Windows.Ink.InkAnalyzer>.  
  
> [!NOTE]
>  En este ejemplo se requiere que los reconocedores de escritura a mano estén instalados en el sistema.  
  
 Cree un nuevo proyecto de aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en Visual Studio 2005 denominado InkRecognition.  Reemplace el contenido del archivo Window1.xaml por el siguiente código XAML:  Este código representa la interfaz de usuario de la aplicación.  
  
 [!code-xml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Agregue una referencia a los ensamblados de análisis de entrada de lápiz de WPF IAWinFX.dll, IACore.dll e IALoader.dll, que se encuentran en \\Archivos de programa\\Reference Assemblies\\Microsoft\\Tablet PC\\v1.7.  Reemplace el contenido del archivo de código subyacente por el código siguiente:  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## Vea también  
 <xref:System.Windows.Ink.InkAnalyzer>   
 <xref:System.Windows.Ink.AnalysisStatus>   
 <xref:System.Windows.Controls.InkCanvas>