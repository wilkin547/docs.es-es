---
title: "C&#243;mo: Enlazar un adorno a un elemento | Microsoft Docs"
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
  - "adornos, enlazar a UIElements especificados"
  - "UIElements, enlazar etiquetas contextuales a"
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Enlazar un adorno a un elemento
En este ejemplo se muestra cómo enlazar mediante programación un adorno a un elemento <xref:System.Windows.UIElement> especificado.  
  
## Ejemplo  
 Para enlazar un adorno a un elemento <xref:System.Windows.UIElement> determinado, siga estos pasos:  
  
1.  Llame al método `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para obtener un objeto <xref:System.Windows.Documents.AdornerLayer> del elemento <xref:System.Windows.UIElement> que se va a adornar.  <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> recorre el árbol visual en sentido ascendente, empezando por el elemento **UIElement** especificado, y devuelve la primera capa de adornos que encuentra.  \(Si no se encuentra ninguna capa, el método devuelve null.\)  
  
2.  Llame al método <xref:System.Windows.Documents.AdornerLayer.Add%2A> para enlazar el adorno al elemento **UIElement** de destino.  
  
 En el ejemplo siguiente se enlaza el adorno SimpleCircleAdorner \(mostrado anteriormente\) a un control <xref:System.Windows.Controls.TextBox> denominado *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.  
  
## Vea también  
 [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)