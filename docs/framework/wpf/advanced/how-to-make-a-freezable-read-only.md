---
title: Procedimiento Hacer que un elemento Freezable sea de sólo lectura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: e0cc5d73f9b9f15fc02bf20a70c84da1a7c535c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671673"
---
# <a name="how-to-make-a-freezable-read-only"></a>Procedimiento Hacer que un elemento Freezable sea de sólo lectura
En este ejemplo se muestra cómo realizar una <xref:System.Windows.Freezable> de solo lectura mediante una llamada a su <xref:System.Windows.Freezable.Freeze%2A> método.  
  
 No se puede inmovilizar un <xref:System.Windows.Freezable> objeto si alguna de las condiciones siguientes es `true` sobre el objeto:  
  
-   Ha animado o propiedades enlazado a datos.  
  
-   Tiene propiedades establecidas por un recurso dinámico. Para obtener más información acerca de los recursos dinámicos, consulte el [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Contiene <xref:System.Windows.Freezable> subobjetos que no se puede inmovilizar.  
  
 Si estas condiciones son `false` para su <xref:System.Windows.Freezable> objeto y no va a modificar, considere la posibilidad de inmovilizarlo para obtener ventajas de rendimiento.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se inmoviliza un <xref:System.Windows.Media.SolidColorBrush>, que es un tipo de <xref:System.Windows.Freezable> objeto.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Para obtener más información acerca de <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
