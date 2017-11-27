---
title: "Cómo: Alinear horizontal o verticalmente el contenido de un elemento StackPanel"
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
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bccf0455c736d14bd77113841603022d4c362787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>Cómo: Alinear horizontal o verticalmente el contenido de un elemento StackPanel
Este ejemplo muestra cómo ajustar la <xref:System.Windows.Controls.StackPanel.Orientation%2A> de contenido dentro de un <xref:System.Windows.Controls.StackPanel> elemento y también cómo ajustar la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> del contenido secundario.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea tres <xref:System.Windows.Controls.ListBox> elementos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Cada <xref:System.Windows.Controls.ListBox> representa los valores posibles de la <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> propiedades de un <xref:System.Windows.Controls.StackPanel>. Cuando un usuario selecciona un valor en cualquiera de los <xref:System.Windows.Controls.ListBox> elementos, la propiedad asociada de la <xref:System.Windows.Controls.StackPanel> y su elemento secundario <xref:System.Windows.Controls.Button> cambiar elementos.  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 El siguiente archivo de código subyacente define los cambios a los eventos que están asociados a la <xref:System.Windows.Controls.ListBox> cambios de selección. <xref:System.Windows.Controls.StackPanel>se identifica mediante el <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
