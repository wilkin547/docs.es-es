---
title: "C&#243;mo: Definir m&#225;rgenes de elementos y controles | Microsoft Docs"
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
  - "Margin (propiedad), establecer"
  - "propiedades, Margin (propiedad)"
  - "establecer, Margin (propiedad)"
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Definir m&#225;rgenes de elementos y controles
En este ejemplo se describe cómo establecer la propiedad <xref:System.Windows.FrameworkElement.Margin%2A>, cambiando cualquier valor de propiedad existente para el margen en el código subyacente.  La propiedad <xref:System.Windows.FrameworkElement.Margin%2A> es una propiedad del elemento base <xref:System.Windows.FrameworkElement>, por lo que la heredan diversos controles y otros elementos.  
  
 Este ejemplo está escrito en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], con un archivo de código subyacente al que hace referencia el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  El subyacente se muestra en versión [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] y en versión [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)].  
  
## Ejemplo  
 [!code-xml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]