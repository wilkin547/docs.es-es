---
title: 'Cómo: Alinear horizontal o verticalmente el contenido de un elemento StackPanel'
description: Obtenga información sobre cómo ajustar la orientación del contenido en un Windows Presentation Foundation StackPanel y el HorizontalAlignment y el VerticalAlignment del contenido secundario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: d3c7215d8193d1d8a72597c44cf265f5bd400ea1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167628"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>Cómo: Alinear horizontal o verticalmente el contenido de un elemento StackPanel
En este ejemplo se muestra cómo ajustar el <xref:System.Windows.Controls.StackPanel.Orientation%2A> contenido dentro de un <xref:System.Windows.Controls.StackPanel> elemento y también cómo ajustar el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> contenido secundario.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se crean tres <xref:System.Windows.Controls.ListBox> elementos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . Cada <xref:System.Windows.Controls.ListBox> representa los valores posibles de las <xref:System.Windows.Controls.StackPanel.Orientation%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedades, y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> de <xref:System.Windows.Controls.StackPanel> . Cuando un usuario selecciona un valor en cualquiera de los <xref:System.Windows.Controls.ListBox> elementos, la propiedad asociada de <xref:System.Windows.Controls.StackPanel> y sus elementos secundarios <xref:System.Windows.Controls.Button> cambian.  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 El siguiente archivo de código subyacente define los cambios en los eventos que están asociados a los <xref:System.Windows.Controls.ListBox> cambios de la selección. <xref:System.Windows.Controls.StackPanel>se identifica mediante <xref:System.Windows.FrameworkElement.Name%2A> `sp1` .  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [Información general sobre elementos Panel](panels-overview.md)
