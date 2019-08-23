---
title: Procedimiento Establecer el alto de una ventana desde una página
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c1041af88241011b51c96d7b61423344a32b25ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940799"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>Procedimiento Establecer el alto de una ventana desde una página
En este ejemplo se muestra cómo establecer el alto de la ventana desde un <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Ejemplo  
 Un <xref:System.Windows.Controls.Page> puede establecer el alto de su ventana <xref:System.Windows.Controls.Page.WindowHeight%2A>host estableciendo. Esta propiedad permite <xref:System.Windows.Controls.Page> que no tenga conocimiento explícito del tipo de ventana que lo hospeda.  
  
> [!NOTE]
> Para establecer el alto de una ventana mediante <xref:System.Windows.Controls.Page.WindowHeight%2A> <xref:System.Windows.Controls.Page> , debe ser el elemento secundario de una ventana.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
