---
title: Buscar y resaltar texto mediante UI Automation
description: Buscar y resaltar texto mediante la automatización de la interfaz de usuario. Un ejemplo busca y resalta de forma secuencial cada aparición de una cadena en el contenido del control de texto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: 7ae933bdf12c81e48371fa89ba5fc5cf5dd4731e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276469"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="78a16-104">Buscar y resaltar texto mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="78a16-104">Find and Highlight Text Using UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="78a16-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="78a16-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="78a16-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="78a16-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="78a16-107">En este tema se muestra cómo buscar y resaltar secuencialmente cada aparición de una cadena en el contenido de un control de texto mediante [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78a16-107">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="78a16-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78a16-108">Example</span></span>  

 <span data-ttu-id="78a16-109">En el ejemplo siguiente se obtiene un <xref:System.Windows.Automation.TextPattern> objeto de un control de texto.</span><span class="sxs-lookup"><span data-stu-id="78a16-109">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="78a16-110"><xref:System.Windows.Automation.Text.TextPatternRange>A continuación, se crea un objeto que representa el contenido textual del documento completo utilizando la <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> propiedad de <xref:System.Windows.Automation.TextPattern> .</span><span class="sxs-lookup"><span data-stu-id="78a16-110">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="78a16-111"><xref:System.Windows.Automation.Text.TextPatternRange>A continuación, se crean dos objetos adicionales para la funcionalidad de búsqueda y resaltado secuencial.</span><span class="sxs-lookup"><span data-stu-id="78a16-111">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="78a16-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="78a16-112">See also</span></span>

- [<span data-ttu-id="78a16-113">Buscar y resaltar texto mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="78a16-113">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
