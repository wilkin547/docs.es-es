---
title: "C&#243;mo: Establecer las propiedades de alto de un elemento | Microsoft Docs"
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
  - "propiedades de alto"
  - "Panel (control), propiedades de alto de los elementos"
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Establecer las propiedades de alto de un elemento
## Ejemplo  
 En este ejemplo se muestran los distintos comportamientos de representación de las cuatro propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] que están relacionadas con el alto.  
  
 La clase <xref:System.Windows.FrameworkElement> expone cuatro propiedades que describen las características de alto de un elemento.  Estas cuatro propiedades pueden generar conflictos y, en ese caso, el valor que tiene prioridad se determina de la manera siguiente: el valor de <xref:System.Windows.FrameworkElement.MinHeight%2A> tiene prioridad sobre el valor de <xref:System.Windows.FrameworkElement.MaxHeight%2A>, que a su vez tiene prioridad sobre el valor de <xref:System.Windows.FrameworkElement.Height%2A>.  Una cuarta propiedad, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, es de solo lectura y notifica el alto real tal y como se determina por las interacciones con el proceso del diseño.  
  
 En los siguientes ejemplos de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] se dibuja un elemento <xref:System.Windows.Shapes.Rectangle> \(`rect1`\) como un elemento secundario de <xref:System.Windows.Controls.Canvas>.  Puede cambiar las propiedades de alto de una clase <xref:System.Windows.Shapes.Rectangle> por medio de una serie de elementos <xref:System.Windows.Controls.ListBox> que representan los valores de propiedad de <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.  De esta manera, la prioridad de cada propiedad se muestra visualmente.  
  
 [!code-xml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 Los siguientes ejemplos de código subyacente permiten controlar los eventos que provoca el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.  Cada controlador toma la entrada de <xref:System.Windows.Controls.ListBox>, analiza el valor como <xref:System.Double> y aplica el valor a la propiedad relacionada con el alto especificada.  Los valores de alto se convierten también en una cadena y se escriben en varios elementos <xref:System.Windows.Controls.TextBlock> \(la definición de esos elementos no se muestra en el código XAML seleccionado\).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Para obtener el ejemplo completo, vea [Height Properties Sample](http://go.microsoft.com/fwlink/?LinkID=159993).  
  
## Vea también  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>   
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>   
 <xref:System.Windows.FrameworkElement.MinHeight%2A>   
 <xref:System.Windows.FrameworkElement.Height%2A>   
 [Establecer las propiedades de ancho de un elemento](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Ejemplo Height Properties](http://go.microsoft.com/fwlink/?LinkID=159993)