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
ms.openlocfilehash: e4aca4b5ccdbc429a3d6267afc09b9f8b99cd7e9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164192"
---
# <a name="find-and-highlight-text-using-ui-automation"></a>Buscar y resaltar texto mediante UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se muestra cómo buscar y resaltar secuencialmente cada aparición de una cadena en el contenido de un control de texto mediante [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene un <xref:System.Windows.Automation.TextPattern> objeto de un control de texto. <xref:System.Windows.Automation.Text.TextPatternRange>A continuación, se crea un objeto que representa el contenido textual del documento completo utilizando la <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> propiedad de <xref:System.Windows.Automation.TextPattern> . <xref:System.Windows.Automation.Text.TextPatternRange>A continuación, se crean dos objetos adicionales para la funcionalidad de búsqueda y resaltado secuencial.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a>Vea también

- [Buscar y resaltar texto mediante UI Automation](find-and-highlight-text-using-ui-automation.md)
