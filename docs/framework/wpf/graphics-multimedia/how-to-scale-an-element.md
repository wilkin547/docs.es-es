---
title: "C&#243;mo: Ajustar la escala de un elemento | Microsoft Docs"
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
  - "clases, ScaleTransform"
  - "gráficos, ajustar la escala de elementos"
  - "ScaleTransform (clase)"
  - "ajustar la escala, elementos"
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Ajustar la escala de un elemento
En este ejemplo se muestra cómo usar un objeto <xref:System.Windows.Media.ScaleTransform> para ajustar la escala de un elemento.  
  
 Use las propiedades <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> para ajustar la escala del elemento según el factor especificado.  Por ejemplo, un valor de <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> de 1,5 expande el elemento al 150 por ciento de su ancho original.  Un valor de <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> de 0,5 reduce el alto de un elemento a la mitad.  
  
 Use las propiedades <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A> para especificar el punto central de la operación de ajuste de la escala.  De manera predeterminada, <xref:System.Windows.Media.ScaleTransform> se centra en el punto \(0,0\), que corresponde a la esquina superior izquierda del rectángulo.  Esto tiene el efecto de mover el elemento y de hacerlo parecer mayor, porque al aplicar <xref:System.Windows.Media.Transform>, cambia el espacio de coordenadas en que reside el objeto.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.ScaleTransform> para duplicar el tamaño de un <xref:System.Windows.Shapes.Rectangle> de 50 por 50.  <xref:System.Windows.Media.ScaleTransform> tiene un valor de 0 \(el valor predeterminado\) para <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y para <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## Ejemplo  
 [!code-xml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 Normalmente, <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A> se establecen en el centro del objeto cuya escala se ajusta: \(<xref:System.Windows.FrameworkElement.Width%2A>\/2, <xref:System.Windows.FrameworkElement.Height%2A>\/2\).  
  
 En el ejemplo siguiente se muestra otro <xref:System.Windows.Shapes.Rectangle> cuyo tamaño se duplica; sin embargo, en este caso <xref:System.Windows.Media.ScaleTransform> tiene un valor de 25 para <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y para <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, lo que corresponde al centro del rectángulo.  
  
 [!code-xml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 En la ilustración siguiente se muestra la diferencia entre las dos operaciones <xref:System.Windows.Media.ScaleTransform>.  La línea de puntos muestra el tamaño y la posición del rectángulo antes de ajustar su escala.  
  
 ![escalas dobles con diferentes centros](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.png "wcpsdk\_graphicsmm\_scalecenter")  
Dos operaciones de ScaleTransform con valores idénticos de las propiedades ScaleX y ScaleY pero con centros diferentes  
  
 Para obtener el ejemplo completo, vea [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Vea también  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.ScaleTransform>   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)