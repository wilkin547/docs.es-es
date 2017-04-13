---
title: "C&#243;mo: Dibujar texto en el fondo de un control | Microsoft Docs"
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
  - "fondos, dibujar texto en"
  - "controles, dibujar texto en el fondo"
  - "dibujar, texto en el fondo de los controles"
  - "texto, dibujar en el fondo de los controles"
  - "tipografía, dibujar texto en el fondo de los controles"
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Dibujar texto en el fondo de un control
Puede dibujar directamente el texto en el fondo de un control; para ello, convierta una cadena de texto en un objeto <xref:System.Windows.Media.FormattedText> y, a continuación, dibuje el objeto en el objeto <xref:System.Windows.Media.DrawingContext> del control.  También puede utilizar esta técnica para dibujar en el fondo de objetos derivados de <xref:System.Windows.Controls.Panel>, tales como <xref:System.Windows.Controls.Canvas> y <xref:System.Windows.Controls.StackPanel>.  
  
 ![Controles mostrando texto como fondo](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
Ejemplo de controles con fondos de texto personalizados  
  
## Ejemplo  
 Para dibujar en el fondo de un control, cree un nuevo objeto <xref:System.Windows.Media.DrawingBrush> y dibuje el texto convertido en el <xref:System.Windows.Media.DrawingContext> del objeto.  A continuación, asigne el nuevo <xref:System.Windows.Media.DrawingBrush> a la propiedad de fondo del control.  
  
 En el ejemplo de código siguiente se muestra cómo crear un objeto <xref:System.Windows.Media.FormattedText> y dibujar en el fondo de un objeto <xref:System.Windows.Controls.Label> y un objeto <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## Vea también  
 <xref:System.Windows.Media.FormattedText>   
 [Dibujar texto con formato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)