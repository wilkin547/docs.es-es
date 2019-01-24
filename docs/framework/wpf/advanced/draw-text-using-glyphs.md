---
title: Dibujar texto mediante glifos
ms.date: 03/30/2017
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
ms.openlocfilehash: 7c7c4946d2c5cc2aa9001cf119b969dd375a1050
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680249"
---
# <a name="draw-text-using-glyphs"></a>Dibujar texto mediante glifos
En este tema se explica cómo usar el bajo nivel <xref:System.Windows.Documents.Glyphs> objeto para mostrar texto en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran cómo definir las propiedades de un <xref:System.Windows.Documents.Glyphs> objeto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. El <xref:System.Windows.Documents.Glyphs> objeto representa la salida de un <xref:System.Windows.Media.GlyphRun> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. En los ejemplos se supone que las fuentes Arial, Courier New y Times New Roman están instaladas en la carpeta C:\WINDOWS\Fonts del equipo local.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 En este ejemplo se muestra cómo definir otras propiedades de <xref:System.Windows.Documents.Glyphs> objetos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Vea también
- [Tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)
