---
title: 'Cómo: Especificar la dirección del enlace'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 8f7d843382ee3409047d7cf9549267d582883984
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459098"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Cómo: especificar la dirección del enlace

En este ejemplo se muestra cómo especificar si los enlaces actualizan solo la propiedad de destino del enlace (destino), la propiedad de origen del enlace (origen), o las propiedades de destino y origen.  
  
## <a name="example"></a>Ejemplo  
 La propiedad <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> se utiliza para especificar la dirección del enlace. A continuación se muestran las opciones disponibles para las actualizaciones de enlace:  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> actualiza la propiedad de destino o la propiedad cada vez que cambia la propiedad de destino o la propiedad de origen.  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> actualiza la propiedad de destino solo cuando cambia la propiedad de origen.  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> actualiza la propiedad de destino solo cuando se inicia la aplicación o cuando el <xref:System.Windows.FrameworkElement.DataContext%2A> sufre un cambio.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> actualiza la propiedad de origen cuando cambia la propiedad de destino.  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> hace que se use el valor predeterminado de <xref:System.Windows.Data.Binding.Mode%2A> de la propiedad de destino.  
  
 Para obtener más información, vea la enumeración <xref:System.Windows.Data.BindingMode>.  
  
 En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Para detectar los cambios de origen (aplicables a los enlaces <xref:System.Windows.Data.BindingMode.OneWay> y <xref:System.Windows.Data.BindingMode.TwoWay>), el origen debe implementar un mecanismo de notificación de cambio de propiedad adecuado como <xref:System.ComponentModel.INotifyPropertyChanged>. Vea [implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md) para obtener un ejemplo de una implementación de <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 En el caso de los enlaces <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource>, puede controlar el tiempo de las actualizaciones de origen estableciendo la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>. Vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para obtener más información.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.Binding>
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
