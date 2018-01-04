---
title: "Cómo: establecer el ancho de una ventana desde una página"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc9843d4a0f76547b76698a9686b5c4936baa322
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Cómo: establecer el ancho de una ventana desde una página
Este ejemplo muestra cómo establecer el ancho de la ventana de un <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Ejemplo  
 A <xref:System.Windows.Controls.Page> puede establecer el ancho de su ventana host estableciendo <xref:System.Windows.Controls.Page.WindowWidth%2A>. Esta propiedad permite el <xref:System.Windows.Controls.Page> no tenga un conocimiento explícito del tipo de ventana que lo hospeda.  
  
> [!NOTE]
>  Para establecer el ancho de una ventana con <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> debe ser el elemento secundario de una ventana.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
