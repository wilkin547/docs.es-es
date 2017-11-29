---
title: Dibujar texto mediante glifos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ebce286cd93355feac7e4675ef6b142862740a92
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="draw-text-using-glyphs"></a><span data-ttu-id="3e2c1-102">Dibujar texto mediante glifos</span><span class="sxs-lookup"><span data-stu-id="3e2c1-102">Draw Text Using Glyphs</span></span>
<span data-ttu-id="3e2c1-103">Este tema explica cómo utilizar el nivel bajo <xref:System.Windows.Documents.Glyphs> objeto para mostrar texto en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e2c1-103">This topic explains how to use the low-level <xref:System.Windows.Documents.Glyphs> object to display text in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e2c1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e2c1-104">Example</span></span>  
 <span data-ttu-id="3e2c1-105">Los ejemplos siguientes muestran cómo definir las propiedades de un <xref:System.Windows.Documents.Glyphs> objeto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e2c1-105">The following examples show how to define properties for a <xref:System.Windows.Documents.Glyphs> object in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="3e2c1-106">El <xref:System.Windows.Documents.Glyphs> objeto representa la salida de un <xref:System.Windows.Media.GlyphRun> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e2c1-106">The <xref:System.Windows.Documents.Glyphs> object represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="3e2c1-107">En los ejemplos se supone que las fuentes Arial, Courier New y Times New Roman están instaladas en la carpeta C:\WINDOWS\Fonts del equipo local.</span><span class="sxs-lookup"><span data-stu-id="3e2c1-107">The examples assume that the Arial, Courier New, and Times New Roman fonts are installed in the C:\WINDOWS\Fonts folder on the local computer.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="3e2c1-108">Este ejemplo muestra cómo definir otras propiedades de <xref:System.Windows.Documents.Glyphs> objetos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e2c1-108">This example shows how to define other properties of <xref:System.Windows.Documents.Glyphs> objects in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3e2c1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e2c1-109">See Also</span></span>  
 [<span data-ttu-id="3e2c1-110">Tipografía en WPF</span><span class="sxs-lookup"><span data-stu-id="3e2c1-110">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)
