---
title: Buscar y resaltar texto mediante UI Automation
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
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 1a356e2872f803d393015574c380c5f99110074e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185607"
---
# <a name="find-and-highlight-text-using-ui-automation"></a>Buscar y resaltar texto mediante UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestra cómo buscar secuencialmente y resaltar cada aparición de una cadena dentro del contenido de un control de texto mediante [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene un <xref:System.Windows.Automation.TextPattern> objeto a partir de un control de texto. Un <xref:System.Windows.Automation.Text.TextPatternRange> objeto que representa el contenido textual de todo el documento, a continuación, se crea mediante la <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> propiedad de este <xref:System.Windows.Automation.TextPattern>. Dos adicionales <xref:System.Windows.Automation.Text.TextPatternRange> objetos, a continuación, se crean para la búsqueda secuencial y resaltar la funcionalidad.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a>Vea también  
 [Búsqueda y resaltado de texto mediante Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
