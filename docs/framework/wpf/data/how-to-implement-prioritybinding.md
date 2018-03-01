---
title: "Cómo: Implementar PriorityBinding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e6ab8826f2298a8660a85d739fbe3456374b476
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-implement-prioritybinding"></a>Cómo: Implementar PriorityBinding
<xref:System.Windows.Data.PriorityBinding>en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funciona mediante la especificación de una lista de enlaces. Se ordena la lista de enlaces de prioridad más alta a prioridad más baja. Si el enlace de máxima prioridad devuelve un valor correctamente cuando se procesa, a continuación, nunca hay una necesidad de procesar el resto de los enlaces en la lista. Podría ser el caso de que el enlace de máxima prioridad tarda mucho tiempo en evaluarse, se utilizará la siguiente prioridad más alta que devuelve un valor correctamente hasta que un enlace de una prioridad más alta devuelve un valor correctamente.  
  
## <a name="example"></a>Ejemplo  
 Para demostrar cómo <xref:System.Windows.Data.PriorityBinding> funciona, el `AsyncDataSource` se ha creado el objeto con las tres propiedades siguientes: `FastDP`, `SlowerDP`, y `SlowestDP`.  
  
 El descriptor de acceso get de `FastDP` devuelve el valor de la `_fastDP` miembro de datos.  
  
 El descriptor de acceso get de `SlowerDP` espera durante 3 segundos antes de devolver el valor de la `_slowerDP` miembro de datos.  
  
 El descriptor de acceso get de `SlowestDP` esperará 5 segundos antes de devolver el valor de la `_slowestDP` miembro de datos.  
  
> [!NOTE]
>  En este ejemplo es solo con fines de demostración. El [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] directrices se recomiendan definir las propiedades que son órdenes de magnitud más lentas de lo que sería un conjunto de campos. Para obtener más información, consulte [NIB: elegir entre propiedades y métodos](http://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af).  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 El <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad se enlaza a los pasos anteriores `AsyncDS` con <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Cuando el motor de enlace procesa los <xref:System.Windows.Data.Binding> objetos, se inicia con la primera <xref:System.Windows.Data.Binding>, que está enlazado a la `SlowestDP` propiedad. Cuando esto <xref:System.Windows.Data.Binding> está procesado, no devuelve un valor correctamente porque está inactivo durante 5 segundos, por lo que la próxima <xref:System.Windows.Data.Binding> se procesa el elemento. La siguiente <xref:System.Windows.Data.Binding> no devuelve un valor correctamente porque está inactivo durante 3 segundos. El motor de enlace, a continuación, se desplaza al siguiente <xref:System.Windows.Data.Binding> elemento, que está enlazado a la `FastDP` propiedad. Esto <xref:System.Windows.Data.Binding> devuelve el valor "Fast Value". El <xref:System.Windows.Controls.TextBlock> ahora muestra el valor "Fast Value".  
  
 Transcurrido 3 segundos, el `SlowerDP` propiedad devuelve el valor "Slower Value". El <xref:System.Windows.Controls.TextBlock> , a continuación, muestra el valor "Slower Value".  
  
 Transcurrido de 5 segundos, la `SlowestDP` propiedad devuelve el valor "más lento". Ese enlace tiene la prioridad más alta, ya que aparece en primer lugar. El <xref:System.Windows.Controls.TextBlock> ahora muestra el valor "más lento".  
  
 Consulte <xref:System.Windows.Data.PriorityBinding> para obtener información sobre lo que se considera un valor devuelto correctamente de un enlace.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
