---
title: 'Cómo: Enlazar a una enumeración'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454441"
---
# <a name="how-to-bind-to-an-enumeration"></a>Cómo: Enlazar a una enumeración
En este ejemplo se muestra cómo enlazar a una enumeración enlazando al método GetValues de la enumeración.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el <xref:System.Windows.Controls.ListBox> muestra la lista de valores de enumeración de <xref:System.Windows.HorizontalAlignment> a través del enlace de datos. El <xref:System.Windows.Controls.ListBox> y el <xref:System.Windows.Controls.Button> están enlazados de modo que pueda cambiar el valor de la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> del <xref:System.Windows.Controls.Button> seleccionando un valor en el <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>Vea también

- [Enlazar a un método](how-to-bind-to-a-method.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
