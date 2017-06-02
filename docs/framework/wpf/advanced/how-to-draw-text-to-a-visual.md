---
title: "C&#243;mo: Dibujar texto en un elemento visual | Microsoft Docs"
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
  - "dibujar, texto en elementos visuales"
  - "texto, dibujar en elementos visuales"
  - "tipografía, dibujar texto en elementos visuales"
  - "elementos visuales, dibujar texto en"
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Dibujar texto en un elemento visual
En el ejemplo siguiente se muestra cómo dibujar texto en un objeto <xref:System.Windows.Media.DrawingVisual> mediante un objeto <xref:System.Windows.Media.DrawingContext>.  Para devolver un contexto de dibujo, se llama al método <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> de un objeto <xref:System.Windows.Media.DrawingVisual>.  Puede dibujar gráficos y texto en un contexto de dibujo.  
  
 Para dibujar texto en el contexto del dibujo, use el método <xref:System.Windows.Media.DrawingContext.DrawText%2A> de un objeto <xref:System.Windows.Media.DrawingContext>.  Cuando haya terminado de dibujar contenido en el contexto de dibujo, llame al método <xref:System.Windows.Media.DrawingContext.Close%2A> para cerrar el contexto de dibujo y conservar el contenido.  
  
## Ejemplo  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  Para obtener el ejemplo de código completo del que se ha extraído el ejemplo de código anterior, vea [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).