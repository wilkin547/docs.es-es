---
title: "Cómo: Enumerar el contenido de un dibujo de un objeto Visual"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e498bc8e425198e479d7ce0b2328e0efa3ede70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>Cómo: Enumerar el contenido de un dibujo de un objeto Visual
El <xref:System.Windows.Media.Drawing> objeto proporcionar un modelo de objetos para enumerar el contenido de un <xref:System.Windows.Media.Visual>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> método para recuperar el <xref:System.Windows.Media.DrawingGroup> valor de un <xref:System.Windows.Media.Visual> y enumerar.  
  
> [!NOTE]
>  Cuando se enumera el contenido del objeto visual, que se están recuperando <xref:System.Windows.Media.Drawing> objetos y no la representación subyacente de los datos de representación como una lista de instrucciones de gráficos vectoriales. Para más información, consulte [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
