---
title: Procedimiento Establecer el alto de una ventana desde una página
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c99ea134478635f368b71443f43e4d8f772cb5aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007334"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>Procedimiento Establecer el alto de una ventana desde una página
En este ejemplo se muestra cómo establecer el alto de la ventana de un <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Ejemplo  
 Un <xref:System.Windows.Controls.Page> puede establecer el alto de su ventana host estableciendo <xref:System.Windows.Controls.Page.WindowHeight%2A>. Esta propiedad permite el <xref:System.Windows.Controls.Page> no tener conocimiento explícito del tipo de ventana que lo hospeda.  
  
> [!NOTE]
>  Para establecer el alto de una ventana mediante <xref:System.Windows.Controls.Page.WindowHeight%2A>, un <xref:System.Windows.Controls.Page> debe ser el elemento secundario de una ventana.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
