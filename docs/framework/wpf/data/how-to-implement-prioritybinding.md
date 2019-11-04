---
title: 'Cómo: Implementar PriorityBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 343b0aca4736905f3a0cbff5a0f76b170da0c920
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459786"
---
# <a name="how-to-implement-prioritybinding"></a>Cómo: Implementar PriorityBinding
<xref:System.Windows.Data.PriorityBinding> en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funciona especificando una lista de enlaces. La lista de enlaces se ordena de la prioridad más alta a la más baja. Si el enlace de prioridad más alta devuelve un valor correctamente cuando se procesa, no es necesario procesar los otros enlaces de la lista. Podría ser el caso de que el enlace de prioridad más alta tarde mucho tiempo en evaluarse; la siguiente prioridad más alta que devuelve un valor correctamente se usará hasta que un enlace de una prioridad más alta devuelva un valor correctamente.  
  
## <a name="example"></a>Ejemplo  
 Para demostrar cómo funciona <xref:System.Windows.Data.PriorityBinding>, se ha creado el objeto de `AsyncDataSource` con las tres propiedades siguientes: `FastDP`, `SlowerDP`y `SlowestDP`.  
  
 El descriptor de acceso get de `FastDP` devuelve el valor del miembro de datos `_fastDP`.  
  
 El descriptor de acceso get de `SlowerDP` espera 3 segundos antes de devolver el valor del miembro de datos `_slowerDP`.  
  
 El descriptor de acceso get de `SlowestDP` espera 5 segundos antes de devolver el valor del miembro de datos `_slowestDP`.  
  
> [!NOTE]
> Este ejemplo solamente sirve de demostración. Las instrucciones de .NET recomiendan la definición de propiedades que son órdenes de magnitud más lentas que un conjunto de campos. Para obtener más información, vea [elegir entre propiedades y métodos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 La propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> se enlaza a la `AsyncDS` anterior mediante <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Cuando el motor de enlace procesa los objetos <xref:System.Windows.Data.Binding>, se inicia con la primera <xref:System.Windows.Data.Binding>, que está enlazada a la propiedad `SlowestDP`. Cuando se procesa este <xref:System.Windows.Data.Binding>, no devuelve un valor correctamente porque está inactivo durante 5 segundos, por lo que se procesa el siguiente elemento <xref:System.Windows.Data.Binding>. La siguiente <xref:System.Windows.Data.Binding> no devuelve un valor correctamente porque está inactivo durante 3 segundos. A continuación, el motor de enlace se desplaza al siguiente elemento <xref:System.Windows.Data.Binding>, que está enlazado a la propiedad `FastDP`. Esta <xref:System.Windows.Data.Binding> devuelve el valor "Fast Value". En el <xref:System.Windows.Controls.TextBlock> ahora se muestra el valor "Fast Value".  
  
 Transcurridos tres segundos, la propiedad `SlowerDP` devuelve el valor "Slow Value". A continuación, el <xref:System.Windows.Controls.TextBlock> muestra el valor "Slow Value".  
  
 Transcurridos 5 segundos, la propiedad `SlowestDP` devuelve el valor "valor más lento". Dicho enlace tiene la prioridad más alta, ya que se muestra en primer lugar. En el <xref:System.Windows.Controls.TextBlock> ahora se muestra el valor "valor más lento".  
  
 Consulte <xref:System.Windows.Data.PriorityBinding> para obtener información sobre lo que se considera un valor devuelto correcto desde un enlace.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
