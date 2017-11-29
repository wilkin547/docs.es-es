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
ms.openlocfilehash: 7354a6c3f1b913494da9ad45181a0c7741a1cfa2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Cómo: establecer el ancho de una ventana desde una página
Este ejemplo muestra cómo establecer el ancho de la ventana de un <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Ejemplo  
 A <xref:System.Windows.Controls.Page> puede establecer el ancho de su ventana host estableciendo <xref:System.Windows.Controls.Page.WindowWidth%2A>. Esta propiedad permite el <xref:System.Windows.Controls.Page> no tenga un conocimiento explícito del tipo de ventana que lo hospeda.  
  
> [!NOTE]
>  Para establecer el ancho de una ventana con <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> debe ser el elemento secundario de una ventana.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
