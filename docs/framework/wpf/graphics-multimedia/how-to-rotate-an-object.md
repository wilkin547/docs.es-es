---
title: "C&#243;mo: Girar un objeto | Microsoft Docs"
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
  - "gráficos, girar objetos"
  - "girar objetos"
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Girar un objeto
En este ejemplo se muestra cómo girar un objeto.  El ejemplo crea primero un objeto <xref:System.Windows.Media.RotateTransform> y, a continuación, especifica su propiedad <xref:System.Windows.Media.RotateTransform.Angle%2A> en grados.  
  
 En el ejemplo siguiente se gira un objeto <xref:System.Windows.Shapes.Polyline> 45 grados sobre su esquina superior izquierda.  
  
## Ejemplo  
 [!code-xml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Las propiedades <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> del objeto <xref:System.Windows.Media.RotateTransform> especifican el punto sobre el que gira el objeto.  Este punto central se expresa en el espacio de la coordenada del elemento que se transforma.  De forma predeterminada, se aplica la rotación a \(0,0\) que es la esquina superior izquierda del objeto que se va a transformar.  
  
 En el ejemplo siguiente se gira en el sentido de las agujas del reloj un objeto <xref:System.Windows.Shapes.Polyline> 45 grados sobre el punto \(25,50\).  
  
 [!code-xml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 La ilustración siguiente muestra los resultados de aplicar un objeto <xref:System.Windows.Media.Transform> a los dos objetos.  
  
 ![rotaciones de 45 grados con diferentes centros](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.png "wcpsdk\_graphicsmm\_rotatetransform45degrees")  
Dos objetos que giran 45 grados respecto a diferentes centros de rotación  
  
 El objeto <xref:System.Windows.Shapes.Polyline> de los ejemplos anteriores es un objeto <xref:System.Windows.UIElement>.  Al aplicar un objeto <xref:System.Windows.Media.Transform> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> de un control <xref:System.Windows.UIElement>, se puede utilizar la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> para especificar un origen para cada objeto <xref:System.Windows.Media.Transform> que aplique al elemento.  Dado que la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> utiliza coordenadas relativas, se puede aplicar una transformación al centro del elemento aunque no se conozca su tamaño.  Para obtener más información y un ejemplo, vea [Especificar el origen de una transformación utilizando valores relativos](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Para obtener el ejemplo completo, vea [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Vea también  
 <xref:System.Windows.Media.Transform>   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)