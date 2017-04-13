---
title: "C&#243;mo: Sesgar un elemento | Microsoft Docs"
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
  - "clases, SkewTransform"
  - "gráficos, sesgar elementos"
  - "sesgar elementos"
  - "SkewTransform (clase)"
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Sesgar un elemento
En este ejemplo se muestra cómo usar un objeto <xref:System.Windows.Media.SkewTransform> para sesgar un elemento.  Un [sesgo](GTMT), que también se conoce como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme.  <xref:System.Windows.Media.SkewTransform> suele usarse para simular una profundidad [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] en objetos [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)].  
  
 Use las propiedades <xref:System.Windows.Media.SkewTransform.CenterX%2A> y <xref:System.Windows.Media.SkewTransform.CenterY%2A> para especificar el punto central de <xref:System.Windows.Media.SkewTransform>.  
  
 Use las propiedades <xref:System.Windows.Media.SkewTransform.AngleX%2A> y <xref:System.Windows.Media.SkewTransform.AngleY%2A> para especificar el ángulo de sesgo del eje X e Y, así como para sesgar el sistema de coordenadas actual a lo largo de estos ejes.  
  
 Para predecir el efecto de una transformación de sesgo, piense que <xref:System.Windows.Media.SkewTransform.AngleX%2A> sesga los valores del eje X respecto al sistema de coordenadas original.  Por consiguiente, para obtener un <xref:System.Windows.Media.SkewTransform.AngleX%2A> de 30, el eje Y gira 30 grados a través del origen y sesga los valores en X\- 30 grados a partir de ese origen.  Igualmente, un <xref:System.Windows.Media.SkewTransform.AngleY%2A> de 30 sesga los valores de Y\- de la forma 30 grados desde el origen.  Observe que no se trata del mismo efecto que trasladar \(mover\) el sistema de coordenadas 30 grados en X\- o Y\-.  
  
 En el ejemplo siguiente se aplica un sesgo horizontal de 45 grados a un objeto <xref:System.Windows.Shapes.Rectangle> desde un punto central de \(0,0\).  
  
## Ejemplo  
 [!code-xml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 En el ejemplo siguiente se aplica un sesgo horizontal de 45 grados a un objeto <xref:System.Windows.Shapes.Rectangle> desde un punto central de \(25,25\).  
  
 [!code-xml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 En el ejemplo siguiente se aplica un sesgo vertical de 45 grados a un objeto <xref:System.Windows.Shapes.Rectangle> desde un punto central de \(25,25\).  
  
 [!code-xml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 La ilustración siguiente muestra los diferentes sesgos que se usan en este ejemplo.  
  
 ![Ejemplos de SkewTransform](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.png "img\_wcpsdk\_graphicsmm\_skewtransformexample")  
Ilustración de los tres ejemplos de SkewTransform  
  
 Para obtener el ejemplo completo, vea [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Vea también  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.SkewTransform>   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)