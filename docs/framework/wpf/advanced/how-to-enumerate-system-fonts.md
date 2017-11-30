---
title: "Cómo: Enumerar fuentes del sistema"
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
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ae03cbd8828f61011f8d806be32b5827d77b22a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="ad36d-102">Cómo: Enumerar fuentes del sistema</span><span class="sxs-lookup"><span data-stu-id="ad36d-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="ad36d-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad36d-103">Example</span></span>  
 <span data-ttu-id="ad36d-104">En el ejemplo siguiente se muestra cómo enumerar las fuentes de la colección de fuentes del sistema.</span><span class="sxs-lookup"><span data-stu-id="ad36d-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="ad36d-105">El nombre de familia de fuentes de cada <xref:System.Windows.Media.FontFamily> en <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> se agrega como un elemento a un cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="ad36d-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="ad36d-106">Si varias versiones de la misma familia de fuentes residen en el mismo directorio, el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enumeración fuente devuelve la versión más reciente de la fuente.</span><span class="sxs-lookup"><span data-stu-id="ad36d-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="ad36d-107">Si la información de versión no proporciona la resolución, se devuelve la fuente con marca de tiempo más reciente.</span><span class="sxs-lookup"><span data-stu-id="ad36d-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="ad36d-108">Si la información de marca de tiempo es equivalente, se devuelve el archivo de fuente que se encuentra primero en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="ad36d-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>
