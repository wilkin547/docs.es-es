---
title: "Cómo: Utilizar la clase FontSizeConverter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcf2d7348ca5b6b9d3b2edc44f92afbd46d32594
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-the-fontsizeconverter-class"></a>Cómo: Utilizar la clase FontSizeConverter
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra cómo crear una instancia de <xref:System.Windows.FontSizeConverter> y usarlo para cambiar el tamaño de fuente.  
  
 En el ejemplo se define un método personalizado denominado `changeSize` que convierte el contenido de un <xref:System.Windows.Controls.ListBoxItem>, tal como se define en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo a una instancia de <xref:System.Double>y versiones posteriores en un <xref:System.String>. Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a una <xref:System.Windows.FontSizeConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Double>. Este valor, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.TextBlock.FontSize%2A> propiedad de la <xref:System.Windows.Controls.TextBlock> elemento.  
  
 Este ejemplo también define un segundo método personalizado que se denomina `changeFamily`. Este método convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de la <xref:System.Windows.Controls.ListBoxItem> a una <xref:System.String>y, a continuación, pasa ese valor a la <xref:System.Windows.Controls.TextBlock.FontFamily%2A> propiedad de la <xref:System.Windows.Controls.TextBlock> elemento.  
  
 En este ejemplo no se ejecuta.  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FontSizeConverter>
