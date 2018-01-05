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
ms.workload: dotnet
ms.openlocfilehash: 5c97926286076149a6eedf34bb70bbc76b2e0d8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
