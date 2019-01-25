---
title: Procedimiento Activar una animación al cambiar el valor de una propiedad
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 2be85a9ae93d504d98930468ad2e257385e835f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705302"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>Procedimiento Activar una animación al cambiar el valor de una propiedad
En este ejemplo se muestra cómo usar un <xref:System.Windows.Trigger> para iniciar un <xref:System.Windows.Media.Animation.Storyboard> cuando cambia un valor de propiedad. Puede usar un <xref:System.Windows.Trigger> dentro de un <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, o <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Trigger> para animar la <xref:System.Windows.UIElement.Opacity%2A> de un <xref:System.Windows.Controls.Button> cuando su <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad pasa a ser `true`.  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Las animaciones aplicadas por la propiedad <xref:System.Windows.Trigger> se comportan los objetos en un modo más complejo que <xref:System.Windows.EventTrigger> animaciones o animaciones a usar <xref:System.Windows.Media.Animation.Storyboard> métodos.  Se "continúan" con animaciones definida por otros <xref:System.Windows.Trigger> objetos, pero se crean con <xref:System.Windows.EventTrigger> y animaciones activadas por métodos.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Trigger>
- [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
- [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
