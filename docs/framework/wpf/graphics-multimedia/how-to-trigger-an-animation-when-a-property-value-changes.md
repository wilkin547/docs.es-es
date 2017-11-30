---
title: "Cómo: Activar una animación al cambiar el valor de una propiedad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d722be0f0367f7e6e98ef1c8451ce58ee28fedd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>Cómo: Activar una animación al cambiar el valor de una propiedad
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Trigger> para iniciar un <xref:System.Windows.Media.Animation.Storyboard> cuando cambia un valor de propiedad. Puede usar un <xref:System.Windows.Trigger> dentro de un <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, o <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Trigger> para animar la <xref:System.Windows.UIElement.Opacity%2A> de un <xref:System.Windows.Controls.Button> cuando su <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad pasa a ser `true`.  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Las animaciones aplicadas por la propiedad <xref:System.Windows.Trigger> objetos se comportan de forma más compleja que <xref:System.Windows.EventTrigger> copia las animaciones ni animaciones a usar <xref:System.Windows.Media.Animation.Storyboard> métodos.  Se "continúan" con animaciones definida por otros <xref:System.Windows.Trigger> objetos, pero se crean con <xref:System.Windows.EventTrigger> y animaciones activadas por métodos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Trigger>  
 [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
