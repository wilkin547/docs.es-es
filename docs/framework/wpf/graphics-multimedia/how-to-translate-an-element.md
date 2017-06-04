---
title: "C&#243;mo: Trasladar un elemento | Microsoft Docs"
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
  - "clases, TranslateTransform"
  - "gráficos, traslaciones"
  - "TranslateTransform (clase)"
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Trasladar un elemento
En este ejemplo se muestra cómo trasladar \(mover\) un elemento mediante <xref:System.Windows.Media.TranslateTransform>.  
  
 La clase <xref:System.Windows.Media.TranslateTransform> resulta especialmente útil para mover elementos dentro de los paneles que no admiten una posición absoluta.  Por ejemplo, al aplicar <xref:System.Windows.Media.TranslateTransform> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> de un elemento, puede mover un elemento en un objeto <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel>.  
  
 Utilice la propiedad <xref:System.Windows.Media.TranslateTransform.X%2A> de <xref:System.Windows.Media.TranslateTransform> para especificar la cantidad de [píxeles](GTMT) que desea mover el elemento a lo largo del eje X.  Utilice la propiedad <xref:System.Windows.Media.TranslateTransform.Y%2A> para especificar la distancia, en píxeles, que desea mover el elemento a lo largo del eje Y.  Por último, aplique <xref:System.Windows.Media.TranslateTransform> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> del elemento.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.TranslateTransform> para mover un elemento 50 [píxeles](GTMT) a la derecha y 50 píxeles hacia abajo.  
  
## Ejemplo  
 [!code-xml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Para obtener el ejemplo completo, vea [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Vea también  
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)