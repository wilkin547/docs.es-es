---
title: "Cómo: Utilizar un objeto ThicknessConverter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 311998595cb1584c276afc28510e1750c770ae93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-thicknessconverter-object"></a>Cómo: Utilizar un objeto ThicknessConverter
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra cómo crear una instancia de <xref:System.Windows.ThicknessConverter> y usarlo para cambiar el grosor de un borde.  
  
 En el ejemplo se define un método personalizado denominado `changeThickness`; en primer lugar, este método convierte el contenido de un <xref:System.Windows.Controls.ListBoxItem>, tal como se define en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo a una instancia de <xref:System.Windows.Thickness>y más adelante convierte el contenido en un <xref:System.String>. Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a una <xref:System.Windows.ThicknessConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Windows.Thickness>. Este valor, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.Border.BorderThickness%2A> propiedad de la <xref:System.Windows.Controls.Border>.  
  
 En este ejemplo no se ejecuta.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Thickness>  
 <xref:System.Windows.ThicknessConverter>  
 <xref:System.Windows.Controls.Border>  
 [Cómo: cambiar la propiedad Margin](http://msdn.microsoft.com/en-us/8a313efd-5f99-4097-b4c1-8fa49d8379a2)  
 [Cómo: convertir un elemento ListBoxItem en un nuevo tipo de datos](http://msdn.microsoft.com/en-us/7a080b88-184e-4b27-bb61-d42bafba9727)  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
