---
title: Información general sobre TextBlock
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: ce7da2b9c9c8e2a3a24d3acf18396ca447ac3f27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203475"
---
# <a name="textblock-overview"></a>Información general sobre TextBlock
El <xref:System.Windows.Controls.TextBlock> control proporciona compatibilidad con el texto para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones. El elemento se destina principalmente a los escenarios de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] básicos que no requieren más de un párrafo de texto. Admite un número de propiedades que permiten un control preciso de presentación, como <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, y <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>. Contenido de texto se puede agregar utilizando el <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad. Cuando se utiliza en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], el contenido de las etiquetas de apertura y cierre se agrega implícitamente como texto del elemento.  
  
 Un <xref:System.Windows.Controls.TextBlock> elemento puede instanciarse mediante muy simplemente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 De forma similar, el uso de la <xref:System.Windows.Controls.TextBlock> elemento en el código es relativamente sencillo.  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Label>
