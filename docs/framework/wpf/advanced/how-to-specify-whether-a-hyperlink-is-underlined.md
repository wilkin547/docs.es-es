---
title: "C&#243;mo: Especificar el subrayado de un hiperv&#237;nculo | Microsoft Docs"
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
  - "clases, TextDecoration"
  - "Hyperlink (tipo de control)"
  - "TextDecoration (clase)"
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Especificar el subrayado de un hiperv&#237;nculo
El objeto <xref:System.Windows.Documents.Hyperlink> es un elemento de contenido dinámico insertado que permite hospedar hipervínculos dentro del contenido dinámico.  De forma predeterminada, <xref:System.Windows.Documents.Hyperlink> usa un objeto <xref:System.Windows.TextDecoration> para mostrar un subrayado.  Los objetos <xref:System.Windows.TextDecoration> pueden mejorar el rendimiento al crear instancias, especialmente si dispone de muchos objetos <xref:System.Windows.Documents.Hyperlink>.  Si realiza un uso excesivo de elementos <xref:System.Windows.Documents.Hyperlink>, puede ser conveniente mostrar la línea de subrayado únicamente al desencadenar un evento, como el evento <xref:System.Windows.ContentElement.MouseEnter>.  
  
 En el ejemplo siguiente, el subrayado para el vínculo "My MSN" es dinámico: únicamente aparece cuando se activa el evento <xref:System.Windows.ContentElement.MouseEnter>.  
  
 ![Hipervínculos que muestran TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Hipervínculos definidos con TextDecorations  
  
## Ejemplo  
 En el ejemplo de marcado siguiente se muestra <xref:System.Windows.Documents.Hyperlink> con y sin subrayado:  
  
 [!code-xml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 En el ejemplo de código siguiente se muestra cómo crear un subrayado para <xref:System.Windows.Documents.Hyperlink> cuando se produce el evento <xref:System.Windows.ContentElement.MouseEnter> y quitarlo cuando se produce el evento <xref:System.Windows.ContentElement.MouseLeave>.  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## Vea también  
 <xref:System.Windows.TextDecoration>   
 <xref:System.Windows.Documents.Hyperlink>   
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Crear una decoración de texto](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)