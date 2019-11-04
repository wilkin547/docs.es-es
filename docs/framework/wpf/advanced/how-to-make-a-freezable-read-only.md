---
title: 'Cómo: Hacer que un elemento Freezable sea de sólo lectura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460072"
---
# <a name="how-to-make-a-freezable-read-only"></a>Cómo: Hacer que un elemento Freezable sea de sólo lectura
En este ejemplo se muestra cómo crear un <xref:System.Windows.Freezable> de solo lectura llamando a su método <xref:System.Windows.Freezable.Freeze%2A>.  
  
 No se puede inmovilizar un objeto <xref:System.Windows.Freezable> si alguna de las condiciones siguientes se `true` sobre el objeto:  
  
- Tiene propiedades animadas o enlazadas a datos.  
  
- Tiene propiedades establecidas por un recurso dinámico. Para obtener más información sobre los recursos dinámicos, vea los [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Contiene <xref:System.Windows.Freezable> subobjetos que no se pueden inmovilizar.  
  
 Si estas condiciones se `false` para el objeto <xref:System.Windows.Freezable> y no pretende modificarla, considere la posibilidad de inmovilizarla para obtener ventajas de rendimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush>, que es un tipo de <xref:System.Windows.Freezable> objeto.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Para obtener más información acerca de los objetos de <xref:System.Windows.Freezable>, consulte la [información general sobre objetos Freezable](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Información general sobre objetos Freezable](freezable-objects-overview.md)
- [Temas "Cómo..."](base-elements-how-to-topics.md)
