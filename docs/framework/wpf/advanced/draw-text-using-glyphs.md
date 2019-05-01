---
title: Dibujar texto mediante glifos
ms.date: 03/30/2017
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
ms.openlocfilehash: 55bbc50de519d6607a843fcd633f2c07db53109f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010376"
---
# <a name="draw-text-using-glyphs"></a><span data-ttu-id="3b29c-102">Dibujar texto mediante glifos</span><span class="sxs-lookup"><span data-stu-id="3b29c-102">Draw Text Using Glyphs</span></span>
<span data-ttu-id="3b29c-103">En este tema se explica cómo usar el bajo nivel <xref:System.Windows.Documents.Glyphs> objeto para mostrar texto en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b29c-103">This topic explains how to use the low-level <xref:System.Windows.Documents.Glyphs> object to display text in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b29c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b29c-104">Example</span></span>  
 <span data-ttu-id="3b29c-105">Los ejemplos siguientes muestran cómo definir las propiedades de un <xref:System.Windows.Documents.Glyphs> objeto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b29c-105">The following examples show how to define properties for a <xref:System.Windows.Documents.Glyphs> object in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="3b29c-106">El <xref:System.Windows.Documents.Glyphs> objeto representa la salida de un <xref:System.Windows.Media.GlyphRun> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b29c-106">The <xref:System.Windows.Documents.Glyphs> object represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="3b29c-107">En los ejemplos se supone que las fuentes Arial, Courier New y Times New Roman están instaladas en la carpeta C:\WINDOWS\Fonts del equipo local.</span><span class="sxs-lookup"><span data-stu-id="3b29c-107">The examples assume that the Arial, Courier New, and Times New Roman fonts are installed in the C:\WINDOWS\Fonts folder on the local computer.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="3b29c-108">En este ejemplo se muestra cómo definir otras propiedades de <xref:System.Windows.Documents.Glyphs> objetos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b29c-108">This example shows how to define other properties of <xref:System.Windows.Documents.Glyphs> objects in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3b29c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b29c-109">See also</span></span>

- [<span data-ttu-id="3b29c-110">Tipografía en WPF</span><span class="sxs-lookup"><span data-stu-id="3b29c-110">Typography in WPF</span></span>](typography-in-wpf.md)
