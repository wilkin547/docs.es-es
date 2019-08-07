---
title: Procedimiento Especificar la dirección del enlace
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 023cd42ad5fb321e7ffa65f08673cb4145f49af4
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817911"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Procedimiento Especificar la dirección del enlace

En este ejemplo se muestra cómo especificar si los enlaces actualizan solo la propiedad de destino del enlace (destino), la propiedad de origen del enlace (origen), o las propiedades de destino y origen.  
  
## <a name="example"></a>Ejemplo  
 Utilice la <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> propiedad para especificar la dirección del enlace. A continuación se muestran las opciones disponibles para las actualizaciones de enlace:  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>actualiza la propiedad de destino o la propiedad siempre que cambia la propiedad de destino o la propiedad de origen.  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType>actualiza la propiedad de destino solo cuando cambia la propiedad de origen.  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType>actualiza la propiedad de destino solo cuando se inicia la aplicación o <xref:System.Windows.FrameworkElement.DataContext%2A> cuando se sufre un cambio.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType>actualiza la propiedad de origen cuando cambia la propiedad de destino.  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType>hace que se <xref:System.Windows.Data.Binding.Mode%2A> use el valor predeterminado de la propiedad de destino.  
  
 Para obtener más información, vea la enumeración <xref:System.Windows.Data.BindingMode>.  
  
 En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Para detectar los cambios de origen ( <xref:System.Windows.Data.BindingMode.OneWay> aplicables <xref:System.Windows.Data.BindingMode.TwoWay> a los enlaces y), el origen debe implementar un mecanismo de notificación de <xref:System.ComponentModel.INotifyPropertyChanged>cambio de propiedad adecuado como. Vea [implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md) para obtener <xref:System.ComponentModel.INotifyPropertyChanged> un ejemplo de una implementación de.  
  
 En <xref:System.Windows.Data.BindingMode.TwoWay> el <xref:System.Windows.Data.BindingMode.OneWayToSource> caso de los enlaces o, puede controlar la temporización de las actualizaciones de origen <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> estableciendo la propiedad. Vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para obtener más información.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.Binding>
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
