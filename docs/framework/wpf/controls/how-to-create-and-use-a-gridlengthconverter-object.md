---
title: "C&#243;mo: Crear y utilizar un objeto GridLengthConverter | Microsoft Docs"
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
  - "Grid (control), crear, GridLengthConverter (objetos)"
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Crear y utilizar un objeto GridLengthConverter
## Ejemplo  
 En el ejemplo siguiente se muestra cómo crear y utilizar una instancia de <xref:System.Windows.GridLengthConverter>.  En el ejemplo se define un método personalizado denominado `changeCol`, que pasa el control <xref:System.Windows.Controls.ListBoxItem> a un objeto <xref:System.Windows.GridLengthConverter> que convierte la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> de <xref:System.Windows.Controls.ListBoxItem> en una instancia de <xref:System.Windows.GridLength>.  A continuación, el valor convertido se devuelve como valor de la propiedad <xref:System.Windows.Controls.ColumnDefinition.Width%2A> del elemento <xref:System.Windows.Controls.ColumnDefinition>.  
  
 En el ejemplo también se define un segundo método personalizado, denominado `changeColVal`.  Este método personalizado convierte la propiedad <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> de <xref:System.Windows.Controls.Slider> en un valor <xref:System.String> y, a continuación, devuelve el valor al objeto <xref:System.Windows.Controls.ColumnDefinition> como propiedad <xref:System.Windows.Controls.ColumnDefinition.Width%2A> del elemento.  
  
 Observe que un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] independiente define el contenido del objeto <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-csharp[gridlengthConverterGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## Vea también  
 <xref:System.Windows.GridLengthConverter>   
 <xref:System.Windows.GridLength>