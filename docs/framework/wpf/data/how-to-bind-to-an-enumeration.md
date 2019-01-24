---
title: Procedimiento Enlazar a una enumeración
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: db7b02a961c148bbdc31b05e7c71ea5b5d301c54
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586571"
---
# <a name="how-to-bind-to-an-enumeration"></a>Procedimiento Enlazar a una enumeración
En este ejemplo se muestra cómo enlazar a una enumeración enlazando al método GetValues de la enumeración.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la <xref:System.Windows.Controls.ListBox> muestra la lista de <xref:System.Windows.HorizontalAlignment> valores de enumeración mediante enlace de datos. El <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.Button> se enlazan de forma que pueda cambiar la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> el valor de propiedad el <xref:System.Windows.Controls.Button> seleccionando un valor en el <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Vea también
- [Enlazar a un método](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
