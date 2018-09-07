---
title: 'Cómo: Implementar PriorityBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: a7729ec3d06ec701cf2194bed5d90b5bed76573a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803007"
---
# <a name="how-to-implement-prioritybinding"></a>Cómo: Implementar PriorityBinding
<xref:System.Windows.Data.PriorityBinding> en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funciona mediante la especificación de una lista de enlaces. La lista de enlaces está ordenada de prioridad más alta a prioridad más baja. Si el enlace de máxima prioridad devuelve un valor correctamente cuando se procesa, a continuación, hay nunca una necesidad de procesar los otros enlaces en la lista. Podría ser el caso de que el enlace de máxima prioridad tarda mucho tiempo en evaluarse, se usará la siguiente prioridad más alta que devuelve un valor correctamente hasta que un enlace de una prioridad más alta devuelve un valor correctamente.  
  
## <a name="example"></a>Ejemplo  
 Para demostrar cómo <xref:System.Windows.Data.PriorityBinding> funciona, el `AsyncDataSource` se ha creado el objeto con las tres propiedades siguientes: `FastDP`, `SlowerDP`, y `SlowestDP`.  
  
 El descriptor de acceso get de `FastDP` devuelve el valor de la `_fastDP` miembro de datos.  
  
 El descriptor de acceso get de `SlowerDP` espera 3 segundos antes de devolver el valor de la `_slowerDP` miembro de datos.  
  
 El descriptor de acceso get de `SlowestDP` espera 5 segundos antes de devolver el valor de la `_slowestDP` miembro de datos.  
  
> [!NOTE]
>  Este ejemplo solamente sirve de demostración. El [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] directrices recomiendan definir las propiedades que son órdenes de magnitud más lentas de un conjunto de campos. Para obtener más información, consulte [NIB: elegir entre propiedades y métodos](https://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af).  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 El <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad enlaza a la anterior `AsyncDS` mediante <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Cuando se procesa el motor de enlace el <xref:System.Windows.Data.Binding> objetos, comienza con la primera <xref:System.Windows.Data.Binding>, que se enlaza a la `SlowestDP` propiedad. Cuando esto <xref:System.Windows.Data.Binding> está procesado, no devuelve un valor correctamente porque está inactivo durante 5 segundos, por lo que la próxima <xref:System.Windows.Data.Binding> se procesa el elemento. La próxima <xref:System.Windows.Data.Binding> no devuelve un valor correctamente porque está inactivo durante 3 segundos. El motor de enlace, a continuación, se mueve a la siguiente <xref:System.Windows.Data.Binding> elemento, que está enlazado a la `FastDP` propiedad. Esto <xref:System.Windows.Data.Binding> devuelve el valor "Fast Value". El <xref:System.Windows.Controls.TextBlock> ahora muestra el valor "Fast Value".  
  
 Transcurridos tres segundos, el `SlowerDP` propiedad devuelve el valor "más lento". El <xref:System.Windows.Controls.TextBlock> , a continuación, muestra el valor "más lento".  
  
 Transcurridos cinco segundos, el `SlowestDP` propiedad devuelve el valor "más lento". Ese enlace tiene la prioridad más alta porque aparece en primer lugar. El <xref:System.Windows.Controls.TextBlock> ahora muestra el valor "más lento".  
  
 Consulte <xref:System.Windows.Data.PriorityBinding> para obtener información acerca de qué se considera un valor devuelto correctamente de un enlace.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
