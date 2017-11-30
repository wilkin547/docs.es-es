---
title: "Cómo: Determinar si un elemento Freezable está inmovilizado"
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
helpviewer_keywords: Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47fb0a871c3792450386c440629ead1ee3fbecdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>Cómo: Determinar si un elemento Freezable está inmovilizado
Este ejemplo muestra cómo determinar si un <xref:System.Windows.Freezable> objeto está inmovilizado. Si intenta modificar inmovilizado <xref:System.Windows.Freezable> de objeto, produce un <xref:System.InvalidOperationException>. Para evitar que se produzca esta excepción, use la <xref:System.Windows.Freezable.IsFrozen%2A> propiedad de la <xref:System.Windows.Freezable> objeto para determinar si está inmovilizado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush> y, a continuación, se comprueba mediante la <xref:System.Windows.Freezable.IsFrozen%2A> propiedad para determinar si está inmovilizado.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Para obtener más información acerca de <xref:System.Windows.Freezable> los objetos, vea la [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.IsFrozen%2A>  
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
