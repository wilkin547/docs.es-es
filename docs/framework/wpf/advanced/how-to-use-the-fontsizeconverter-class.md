---
title: "C&#243;mo: Utilizar la clase FontSizeConverter | Microsoft Docs"
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
  - "FontSizeConverter (objetos)"
  - "tipografía, FontSizeConverter (objetos)"
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Utilizar la clase FontSizeConverter
## Ejemplo  
 En este ejemplo se muestra cómo crear una instancia de <xref:System.Windows.FontSizeConverter> y utilizarla para cambiar un tamaño de fuente.  
  
 En el ejemplo se define un método personalizado denominado `changeSize` que convierte el contenido de <xref:System.Windows.Controls.ListBoxItem>, definido en un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] independiente, en una instancia de <xref:System.Double> y, a continuación, en un valor de tipo <xref:System.String>.  Este método pasa <xref:System.Windows.Controls.ListBoxItem> a un objeto <xref:System.Windows.FontSizeConverter>, que convierte la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> en una instancia de <xref:System.Double>.  A continuación, este valor se devuelve como valor de la propiedad <xref:System.Windows.Controls.TextBlock.FontSize%2A> del elemento <xref:System.Windows.Controls.TextBlock>.  
  
 En este ejemplo también se define un segundo método personalizado, denominado `changeFamily`.  Este método convierte la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> de <xref:System.Windows.Controls.ListBoxItem> en un valor <xref:System.String> y, a continuación, pasa el valor a la propiedad <xref:System.Windows.Controls.TextBlock.FontFamily%2A> del elemento <xref:System.Windows.Controls.TextBlock>.  
  
 Este ejemplo no se ejecuta.  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## Vea también  
 <xref:System.Windows.FontSizeConverter>