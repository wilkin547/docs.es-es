---
title: Procedimiento Obtener una copia modificable de un elemento Freezable de solo lectura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942797"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>Procedimiento Obtener una copia modificable de un elemento Freezable de solo lectura
En este ejemplo se muestra cómo usar el <xref:System.Windows.Freezable.Clone%2A> método para crear una copia modificable de solo lectura <xref:System.Windows.Freezable>.  
  
 Después de un <xref:System.Windows.Freezable> objeto está marcado como de solo lectura ("inmovilizado"), no se puede modificar. Sin embargo, puede usar el <xref:System.Windows.Freezable.Clone%2A> método para crear un clon modificable del objeto inmovilizado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un clon modificable de inmovilizado <xref:System.Windows.Media.SolidColorBrush> objeto.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Para obtener más información acerca de <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [Información general sobre objetos Freezable](freezable-objects-overview.md)
- [Temas "Cómo..."](base-elements-how-to-topics.md)
