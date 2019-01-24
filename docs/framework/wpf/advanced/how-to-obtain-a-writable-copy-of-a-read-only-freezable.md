---
title: Procedimiento Obtener una copia modificable de un elemento Freezable de sólo lectura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 2853b1e02e1223cbb2b6dff4acbddb0a41d882cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629961"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>Procedimiento Obtener una copia modificable de un elemento Freezable de sólo lectura
En este ejemplo se muestra cómo usar el <xref:System.Windows.Freezable.Clone%2A> método para crear una copia modificable de solo lectura <xref:System.Windows.Freezable>.  
  
 Después de un <xref:System.Windows.Freezable> objeto está marcado como de solo lectura ("inmovilizado"), no se puede modificar. Sin embargo, puede usar el <xref:System.Windows.Freezable.Clone%2A> método para crear un clon modificable del objeto inmovilizado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un clon modificable de inmovilizado <xref:System.Windows.Media.SolidColorBrush> objeto.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Para obtener más información acerca de <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
