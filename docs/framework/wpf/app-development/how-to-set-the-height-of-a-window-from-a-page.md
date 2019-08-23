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
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="d3637-102">Procedimiento Establecer el alto de una ventana desde una página</span><span class="sxs-lookup"><span data-stu-id="d3637-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="d3637-103">En este ejemplo se muestra cómo establecer el alto de la ventana desde un <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="d3637-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3637-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3637-104">Example</span></span>  
 <span data-ttu-id="d3637-105">Un <xref:System.Windows.Controls.Page> puede establecer el alto de su ventana <xref:System.Windows.Controls.Page.WindowHeight%2A>host estableciendo.</span><span class="sxs-lookup"><span data-stu-id="d3637-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="d3637-106">Esta propiedad permite <xref:System.Windows.Controls.Page> que no tenga conocimiento explícito del tipo de ventana que lo hospeda.</span><span class="sxs-lookup"><span data-stu-id="d3637-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3637-107">Para establecer el alto de una ventana mediante <xref:System.Windows.Controls.Page.WindowHeight%2A> <xref:System.Windows.Controls.Page> , debe ser el elemento secundario de una ventana.</span><span class="sxs-lookup"><span data-stu-id="d3637-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
