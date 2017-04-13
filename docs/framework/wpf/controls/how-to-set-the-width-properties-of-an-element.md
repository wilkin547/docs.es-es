---
title: "C&#243;mo: Establecer las propiedades de ancho de un elemento | Microsoft Docs"
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
  - "Panel (control), propiedades de ancho de los elementos"
  - "propiedades de ancho"
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Establecer las propiedades de ancho de un elemento
## Ejemplo  
 En este ejemplo se muestran los distintos comportamientos de representación de las cuatro propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] que están relacionadas con el ancho.  
  
 La clase <xref:System.Windows.FrameworkElement> expone cuatro propiedades que describen las características de ancho de un elemento.  Estas cuatro propiedades pueden generar conflictos y, en ese caso, el valor que tiene prioridad se determina de la manera siguiente: el valor de <xref:System.Windows.FrameworkElement.MinWidth%2A> tiene prioridad sobre el valor de <xref:System.Windows.FrameworkElement.MaxWidth%2A>, que a su vez tiene prioridad sobre el valor de <xref:System.Windows.FrameworkElement.Width%2A>.  Una cuarta propiedad, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, es de solo lectura y notifica el ancho real tal y como se determina por las interacciones con el proceso del diseño.  
  
 En los siguientes ejemplos de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] se dibuja un elemento <xref:System.Windows.Shapes.Rectangle> \(`rect1`\) como un elemento secundario de <xref:System.Windows.Controls.Canvas>.  Puede cambiar las propiedades de ancho de una clase <xref:System.Windows.Shapes.Rectangle> por medio de una serie de elementos <xref:System.Windows.Controls.ListBox> que representan los valores de propiedad de <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A> y <xref:System.Windows.FrameworkElement.Width%2A>.  De esta manera, la prioridad de cada propiedad se muestra visualmente.  
  
 [!code-xml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 Los siguientes ejemplos de código subyacente permiten controlar los eventos que provoca el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.  Cada método personalizado acepta la entrada de <xref:System.Windows.Controls.ListBox>, analiza el valor como <xref:System.Double> y aplica el valor a la propiedad relacionada con el ancho especificada.  Los valores de ancho se convierten también en una cadena y se escriben en varios elementos <xref:System.Windows.Controls.TextBlock> \(la definición de esos elementos no se muestra en el código XAML seleccionado\).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Para obtener el ejemplo completo, vea [Width Properties Comparison Sample](http://go.microsoft.com/fwlink/?LinkID=160050).  
  
## Vea también  
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.FrameworkElement.ActualWidth%2A>   
 <xref:System.Windows.FrameworkElement.MaxWidth%2A>   
 <xref:System.Windows.FrameworkElement.MinWidth%2A>   
 <xref:System.Windows.FrameworkElement.Width%2A>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Establecer las propiedades de alto de un elemento](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)   
 [Ejemplo Width Properties Comparison](http://go.microsoft.com/fwlink/?LinkID=160050)