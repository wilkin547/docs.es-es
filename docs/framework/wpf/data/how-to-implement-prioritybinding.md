---
title: Procedimiento Implementar PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: ad19db9d686469e3ade1ff188553fceb8d525674
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937443"
---
# <a name="how-to-implement-prioritybinding"></a>Procedimiento Implementar PriorityBinding
<xref:System.Windows.Data.PriorityBinding>en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Works, especificando una lista de enlaces. La lista de enlaces se ordena de la prioridad más alta a la más baja. Si el enlace de prioridad más alta devuelve un valor correctamente cuando se procesa, no es necesario procesar los otros enlaces de la lista. Podría ser el caso de que el enlace de prioridad más alta tarde mucho tiempo en evaluarse; la siguiente prioridad más alta que devuelve un valor correctamente se usará hasta que un enlace de una prioridad más alta devuelva un valor correctamente.  
  
## <a name="example"></a>Ejemplo  
 Para demostrar cómo <xref:System.Windows.Data.PriorityBinding> funciona, el `AsyncDataSource` objeto se ha creado con las tres propiedades siguientes: `FastDP`, `SlowerDP`y `SlowestDP`.  
  
 El descriptor `FastDP` de acceso get de devuelve `_fastDP` el valor del miembro de datos.  
  
 El descriptor `SlowerDP` de acceso get de espera 3 segundos antes de devolver el `_slowerDP` valor del miembro de datos.  
  
 El descriptor `SlowestDP` de acceso get de espera 5 segundos antes de devolver el `_slowestDP` valor del miembro de datos.  
  
> [!NOTE]
> Este ejemplo solamente sirve de demostración. Las [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] instrucciones recomendadas para definir las propiedades que son órdenes de magnitud más lentas que un conjunto de campos serían. Para obtener más información, vea [elegir entre propiedades y métodos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 La <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad se enlaza a la anterior `AsyncDS` mediante <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Cuando el motor de enlace procesa <xref:System.Windows.Data.Binding> los objetos, se inicia con el <xref:System.Windows.Data.Binding>primero, que está enlazado `SlowestDP` a la propiedad. Cuando se procesa, no devuelve un valor correctamente porque está inactivo durante 5 segundos, por lo que se procesa el <xref:System.Windows.Data.Binding> elemento siguiente. <xref:System.Windows.Data.Binding> La siguiente <xref:System.Windows.Data.Binding> no devuelve un valor correctamente porque está inactivo durante 3 segundos. A continuación, el motor de enlace se <xref:System.Windows.Data.Binding> desplaza hasta el siguiente elemento, que `FastDP` está enlazado a la propiedad. Esto <xref:System.Windows.Data.Binding> devuelve el valor "Fast Value". <xref:System.Windows.Controls.TextBlock> Ahora se muestra el valor "Fast Value".  
  
 Transcurridos tres segundos, la `SlowerDP` propiedad devuelve el valor "Slow Value". <xref:System.Windows.Controls.TextBlock> A continuación, se muestra el valor "Slow Value".  
  
 Transcurridos 5 segundos, la `SlowestDP` propiedad devuelve el valor "valor más lento". Dicho enlace tiene la prioridad más alta, ya que se muestra en primer lugar. <xref:System.Windows.Controls.TextBlock> Ahora se muestra el valor "valor más lento".  
  
 Vea <xref:System.Windows.Data.PriorityBinding> para obtener información sobre lo que se considera un valor devuelto correcto desde un enlace.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
