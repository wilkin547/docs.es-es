---
title: "C&#243;mo: Voltear un control UIElement horizontal o verticalmente | Microsoft Docs"
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
  - "voltear UIElements"
  - "UIElements, voltear"
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Voltear un control UIElement horizontal o verticalmente
En este ejemplo se muestra cómo utilizar una transformación <xref:System.Windows.Media.ScaleTransform> para voltear en sentido horizontal o vertical un elemento <xref:System.Windows.UIElement>.  En este ejemplo, se voltea un control <xref:System.Windows.Controls.Button> \(un tipo de elemento <xref:System.Windows.UIElement>\) aplicándole una transformación <xref:System.Windows.Media.ScaleTransform> a su propiedad <xref:System.Windows.UIElement.RenderTransform%2A>.  
  
## Ejemplo  
 En la ilustración siguiente se muestra el botón que se va a voltear.  
  
 ![Botón sin transformación](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.png "graphicsmm\_buttonflipbeforeflip")  
Elemento UIElement que se va a voltear  
  
 A continuación se muestra el código que crea el botón.  
  
 [!code-xml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## Ejemplo  
 Para voltear horizontalmente el botón, cree una transformación <xref:System.Windows.Media.ScaleTransform> y establezca su propiedad <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> en \-1.  Aplique la transformación <xref:System.Windows.Media.ScaleTransform> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> del botón.  
  
 [!code-xml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![Botón volteado horizontalmente alrededor del punto &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.png "graphicsmm\_buttonfliphorizontalflip\_displaced")  
El botón después de aplicar ScaleTransform  
  
## Ejemplo  
 Como puede observar en la ilustración anterior, el botón se ha volteado, pero también se ha movido.  Esto se debe a que se volteó desde su esquina superior izquierda.  Para voltear el botón en su lugar, se debe aplicar <xref:System.Windows.Media.ScaleTransform> a su centro, no a su esquina.  Una manera fácil de aplicar <xref:System.Windows.Media.ScaleTransform> al centro de los botones es establecer la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del botón en 0.5, 0.5.  
  
 [!code-xml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![Botón volteado horizontalmente alrededor de su centro](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.png "graphicsmm\_buttonfliphorizontalflip\_inplace")  
El botón con su propiedad RenderTransformOrigin establecida en 0.5, 0.5  
  
## Ejemplo  
 Para voltear verticalmente el botón, establezca la propiedad <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> del objeto <xref:System.Windows.Media.ScaleTransform> en lugar de su propiedad <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>.  
  
 [!code-xml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![Botón volteado verticalmente alrededor de su centro](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.png "graphicsmm\_buttonflipverticalflip\_inplace")  
El botón volteado en sentido vertical  
  
## Vea también  
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)