---
title: "C&#243;mo: Especificar el origen de una transformaci&#243;n utilizando valores relativos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "gráficos, orígenes de transformaciones"
  - "orígenes de transformaciones"
  - "Transformaciones, orígenes de"
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Especificar el origen de una transformaci&#243;n utilizando valores relativos
En este ejemplo se muestra cómo utilizar valores relativos para especificar el origen de una propiedad <xref:System.Windows.UIElement.RenderTransform%2A> que se aplica a un objeto <xref:System.Windows.FrameworkElement>.  
  
 Al girar, escalar o [sesgar](GTMT) un objeto <xref:System.Windows.FrameworkElement> utilizando la propiedad <xref:System.Windows.UIElement.RenderTransform%2A>, la configuración predeterminada aplica la transformación a la esquina superior izquierda del elemento.  Si desea girar, escala o sesgar desde el centro del elemento, puede compensar estableciendo el centro de la transformación en el centro del elemento.  Sin embargo, para esa solución es necesario que conozca el tamaño del elemento.  Una manera más fácil de aplicar una transformación al centro de un elemento es establecer su propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> en \(0.5, 0.5\), en lugar de establecer un valor de centro en la propia transformación.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza un objeto <xref:System.Windows.Media.RotateTransform> para girar un control 45 grados <xref:System.Windows.Controls.Button> en el sentido de las agujas del reloj.  Dado que el ejemplo no especifica un centro, el botón gira sobre el punto \(0, 0\), que es su esquina superior izquierda.  El objeto <xref:System.Windows.Media.RotateTransform> se aplica a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A>.  
  
 La ilustración siguiente muestra el resultado de la transformación para el ejemplo siguiente.  
  
 ![Botón transformado mediante RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm\_RenderTransformWithDefaultCenter")  
Una rotación de 45 grados en el sentido de las agujas del reloj utilizando la propiedad RenderTransform  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 En el ejemplo siguiente se usa también un objeto <xref:System.Windows.Media.RotateTransform> para girar un <xref:System.Windows.Controls.Button> 45 grados en el sentido de las agujas del reloj; sin embargo, también se establece en el ejemplo la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del botón en \(0,5, 0,5\).  Como consecuencia, la rotación se aplica al centro del botón, en lugar de a la esquina superior izquierda.  
  
 La ilustración siguiente muestra el resultado de la transformación para el ejemplo siguiente.  
  
 ![Botón transformado alrededor de su centro](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm\_RenderTransformRelativeCenter")  
Una rotación de 45 grados utilizando la propiedad RenderTransform con un valor de RenderTransformOrigin de \(0,5, 0,5\)  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Para obtener más información sobre la transformación de objetos, <xref:System.Windows.FrameworkElement>, vea [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
## Vea también  
 <xref:System.Windows.Media.Transform>   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)