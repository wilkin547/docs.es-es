---
title: Procedimiento Determinar si un elemento Freezable está inmovilizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: dee5edc3d8845b00fa6c9aa05c414fd4f912aeb4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592278"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>Procedimiento Determinar si un elemento Freezable está inmovilizado
En este ejemplo se muestra cómo determinar si un <xref:System.Windows.Freezable> objeto está inmovilizado. Si intenta modificar inmovilizado <xref:System.Windows.Freezable> objeto, produce un <xref:System.InvalidOperationException>. Para evitar que se produzca esta excepción, use el <xref:System.Windows.Freezable.IsFrozen%2A> propiedad de la <xref:System.Windows.Freezable> objeto para determinar si se encuentra inmovilizado.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush> y, a continuación, se comprueba mediante la <xref:System.Windows.Freezable.IsFrozen%2A> propiedad para determinar si se encuentra inmovilizado.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Para obtener más información acerca de <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
