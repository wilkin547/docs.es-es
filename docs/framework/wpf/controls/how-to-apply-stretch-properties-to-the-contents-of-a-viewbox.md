---
title: "C&#243;mo: Aplicar propiedades de expansi&#243;n al contenido de un Viewbox | Microsoft Docs"
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
  - "controles, Viewbox"
  - "Stretch (propiedades)"
  - "StretchDirection (propiedades)"
  - "Viewbox (control)"
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Aplicar propiedades de expansi&#243;n al contenido de un Viewbox
## Ejemplo  
 En este ejemplo se muestra cómo cambiar el valor de las propiedades <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> y <xref:System.Windows.Controls.Viewbox.Stretch%2A> de <xref:System.Windows.Controls.Viewbox>.  
  
 El primer ejemplo utiliza [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un elemento <xref:System.Windows.Controls.Viewbox>.  Asigna una propiedad <xref:System.Windows.FrameworkElement.MaxWidth%2A> y una propiedad <xref:System.Windows.FrameworkElement.MaxHeight%2A> de 400.  En el ejemplo se anida un elemento <xref:System.Windows.Controls.Image> en el control <xref:System.Windows.Controls.Viewbox>.  Los elementos <xref:System.Windows.Controls.Button> que corresponden a los valores de propiedad para las enumeraciones <xref:System.Windows.Controls.Viewbox.Stretch%2A> y <xref:System.Windows.Controls.StretchDirection> manipulan el comportamiento de ajuste del objeto <xref:System.Windows.Controls.Image> anidado.  
  
 [!code-xml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 En el archivo de código subyacente siguiente se controlan los eventos <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click> definidos en el ejemplo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anterior.  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## Vea también  
 <xref:System.Windows.Controls.Viewbox>   
 <xref:System.Windows.Media.Stretch>   
 <xref:System.Windows.Controls.StretchDirection>