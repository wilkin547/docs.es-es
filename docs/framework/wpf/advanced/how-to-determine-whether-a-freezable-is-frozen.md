---
title: Filtrar Determinar si un elemento Freezable está inmovilizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 005bb27803830a2e38a7b143d2c4cff669ad1da6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362518"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>Filtrar Determinar si un elemento Freezable está inmovilizado
En este ejemplo se muestra cómo determinar si un <xref:System.Windows.Freezable> objeto está inmovilizado. Si intenta modificar inmovilizado <xref:System.Windows.Freezable> objeto, produce un <xref:System.InvalidOperationException>. Para evitar que se produzca esta excepción, use el <xref:System.Windows.Freezable.IsFrozen%2A> propiedad de la <xref:System.Windows.Freezable> objeto para determinar si se encuentra inmovilizado.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush> y, a continuación, se comprueba mediante la <xref:System.Windows.Freezable.IsFrozen%2A> propiedad para determinar si se encuentra inmovilizado.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Para obtener más información acerca de <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [Información general sobre objetos Freezable](freezable-objects-overview.md)
- [Temas "Cómo..."](base-elements-how-to-topics.md)
