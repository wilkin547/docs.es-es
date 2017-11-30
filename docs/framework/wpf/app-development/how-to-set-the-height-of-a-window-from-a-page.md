---
title: "Cómo: establecer el alto de una ventana desde una página"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29de47eceae4b8927f2701ca0bbda2ecc7243919
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>Cómo: establecer el alto de una ventana desde una página
Este ejemplo muestra cómo establecer el alto de la ventana de un <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Ejemplo  
 A <xref:System.Windows.Controls.Page> puede establecer el alto de su ventana host estableciendo <xref:System.Windows.Controls.Page.WindowHeight%2A>. Esta propiedad permite el <xref:System.Windows.Controls.Page> no tenga un conocimiento explícito del tipo de ventana que lo hospeda.  
  
> [!NOTE]
>  Para establecer el alto de una ventana con <xref:System.Windows.Controls.Page.WindowHeight%2A>, <xref:System.Windows.Controls.Page> debe ser el elemento secundario de una ventana.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
