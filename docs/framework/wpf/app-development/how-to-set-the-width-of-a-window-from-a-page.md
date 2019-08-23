---
title: Procedimiento Establecer el ancho de una ventana desde una página
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: 1e16b75ecb85550facdf24a5b9e341cf0c061178
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940776"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Procedimiento Establecer el ancho de una ventana desde una página
En este ejemplo se muestra cómo establecer el ancho de la ventana desde un <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Ejemplo  
 Un <xref:System.Windows.Controls.Page> puede establecer el ancho de su ventana <xref:System.Windows.Controls.Page.WindowWidth%2A>host estableciendo. Esta propiedad permite <xref:System.Windows.Controls.Page> que no tenga conocimiento explícito del tipo de ventana que lo hospeda.  
  
> [!NOTE]
> Para establecer el ancho de una ventana mediante <xref:System.Windows.Controls.Page.WindowWidth%2A> <xref:System.Windows.Controls.Page> , debe ser el elemento secundario de una ventana.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
