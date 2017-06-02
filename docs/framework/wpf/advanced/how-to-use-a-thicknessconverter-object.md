---
title: "C&#243;mo: Utilizar un objeto ThicknessConverter | Microsoft Docs"
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
  - "grosor del borde"
  - "ThicknessConverter (objetos)"
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Utilizar un objeto ThicknessConverter
## Ejemplo  
 En este ejemplo se muestra cómo crear una instancia de <xref:System.Windows.ThicknessConverter> y usarla para cambiar el grosor de un borde.  
  
 En el ejemplo se define un método personalizado denominado `changeThickness`; este método en primer lugar convierte el contenido de <xref:System.Windows.Controls.ListBoxItem>, tal como se encuentra definido en un archivo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] independiente, en una instancia de <xref:System.Windows.Thickness> y más adelante convierte el contenido en un objeto <xref:System.String>.  Este método pasa <xref:System.Windows.Controls.ListBoxItem> a un objeto <xref:System.Windows.ThicknessConverter>, que convierte la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> en una instancia de <xref:System.Windows.Thickness>.  Este valor se vuelve a recuperar como el valor de la propiedad <xref:System.Windows.Controls.Border.BorderThickness%2A> de <xref:System.Windows.Controls.Border>.  
  
 Este ejemplo no se ejecuta.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Thickness>   
 <xref:System.Windows.ThicknessConverter>   
 <xref:System.Windows.Controls.Border>   
 [How to: Change the Margin Property](http://msdn.microsoft.com/es-es/8a313efd-5f99-4097-b4c1-8fa49d8379a2)   
 [How to: Convert a ListBoxItem to a new Data Type](http://msdn.microsoft.com/es-es/7a080b88-184e-4b27-bb61-d42bafba9727)   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)