---
title: Procedimiento Establecer el ancho de una ventana desde una página
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: fee6d4c9ae9dae03e81cc4be56576763cb59958b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006725"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="19a5e-102">Procedimiento Establecer el ancho de una ventana desde una página</span><span class="sxs-lookup"><span data-stu-id="19a5e-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="19a5e-103">En este ejemplo se muestra cómo establecer el ancho de la ventana de un <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="19a5e-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19a5e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19a5e-104">Example</span></span>  
 <span data-ttu-id="19a5e-105">Un <xref:System.Windows.Controls.Page> puede establecer el ancho de su ventana host estableciendo <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span><span class="sxs-lookup"><span data-stu-id="19a5e-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="19a5e-106">Esta propiedad permite el <xref:System.Windows.Controls.Page> no tener conocimiento explícito del tipo de ventana que lo hospeda.</span><span class="sxs-lookup"><span data-stu-id="19a5e-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19a5e-107">Para establecer el ancho de una ventana mediante <xref:System.Windows.Controls.Page.WindowWidth%2A>, un <xref:System.Windows.Controls.Page> debe ser el elemento secundario de una ventana.</span><span class="sxs-lookup"><span data-stu-id="19a5e-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
