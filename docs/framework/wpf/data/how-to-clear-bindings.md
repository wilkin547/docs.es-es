---
title: Procedimiento Borrar enlaces
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: 8140928d44555e399ddf4ebd73407a251ad3cffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931476"
---
# <a name="how-to-clear-bindings"></a>Procedimiento Borrar enlaces
En este ejemplo se muestra cómo borrar los enlaces de un objeto.  
  
## <a name="example"></a>Ejemplo  
 Para borrar un enlace de una propiedad individual en un objeto, llame a <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> tal como se muestra en el ejemplo siguiente. En el ejemplo siguiente se quita el enlace de la <xref:System.Windows.Controls.TextBlock.TextProperty> de *mytext*, un <xref:System.Windows.Controls.TextBlock> objeto.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Al borrar el enlace, se quita el enlace para que el valor de la propiedad de dependencia cambie al que tendría sin el enlace. Este valor puede ser un valor predeterminado, un valor heredado o un valor de un enlace de la plantilla de datos.  
  
 Para borrar los enlaces de todas las posibles propiedades de un objeto, utilice <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.BindingOperations>
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
