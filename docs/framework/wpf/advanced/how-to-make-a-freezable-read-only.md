---
title: "Cómo: Hacer que un elemento Freezable sea de sólo lectura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa6d3f7109e8258dff0a07556bc8572f6071c961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-freezable-read-only"></a>Cómo: Hacer que un elemento Freezable sea de sólo lectura
Este ejemplo muestra cómo realizar una <xref:System.Windows.Freezable> -solo lectura mediante una llamada a su <xref:System.Windows.Freezable.Freeze%2A> método.  
  
 No se pueden inmovilizar un <xref:System.Windows.Freezable> objeto si alguna de las condiciones siguientes es `true` sobre el objeto:  
  
-   Ha animado o propiedades enlazado a datos.  
  
-   Dicha clase tiene propiedades establecidas por un recurso dinámico. Para obtener más información acerca de recursos dinámicos, consulte el [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Contiene <xref:System.Windows.Freezable> objetos secundarios que no se pueden inmovilizar.  
  
 Si estas condiciones no son `false` para su <xref:System.Windows.Freezable> objeto y no tiene intención de modificarlo, considere la posibilidad de inmovilización para obtener mejoras de rendimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush>, que es un tipo de <xref:System.Windows.Freezable> objeto.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Para obtener más información acerca de <xref:System.Windows.Freezable> los objetos, vea la [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
