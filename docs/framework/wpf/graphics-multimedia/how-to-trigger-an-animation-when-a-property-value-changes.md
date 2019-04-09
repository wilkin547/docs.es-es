---
title: Filtrar Activar una animación al cambiar el valor de una propiedad
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080714"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>Filtrar Activar una animación al cambiar el valor de una propiedad
En este ejemplo se muestra cómo usar un <xref:System.Windows.Trigger> para iniciar un <xref:System.Windows.Media.Animation.Storyboard> cuando cambia un valor de propiedad. Puede usar un <xref:System.Windows.Trigger> dentro de un <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, o <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Trigger> para animar la <xref:System.Windows.UIElement.Opacity%2A> de un <xref:System.Windows.Controls.Button> cuando su <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad pasa a ser `true`.  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Las animaciones aplicadas por la propiedad <xref:System.Windows.Trigger> se comportan los objetos en un modo más complejo que <xref:System.Windows.EventTrigger> animaciones o animaciones a usar <xref:System.Windows.Media.Animation.Storyboard> métodos.  Se "continúan" con animaciones definida por otros <xref:System.Windows.Trigger> objetos, pero se crean con <xref:System.Windows.EventTrigger> y animaciones activadas por métodos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Trigger>
- [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)
- [Información general sobre objetos Storyboard](storyboards-overview.md)
