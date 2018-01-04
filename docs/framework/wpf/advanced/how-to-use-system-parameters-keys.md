---
title: "Cómo: Utilizar claves de parámetros del sistema"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b2a7352540456b459428dd87f6c60be0b8bc08b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-parameters-keys"></a>Cómo: Utilizar claves de parámetros del sistema
Los recursos del sistema exponen varias métricas del sistema como recursos para ayudar a los desarrolladores a crear efectos visuales coherentes con la configuración del sistema. <xref:System.Windows.SystemParameters>es una clase que contiene los valores de parámetro del sistema y las claves de recursos que se enlazan a los valores, por ejemplo, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> y <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>. Las métricas de parámetros del sistema se pueden usar como recursos estáticos o dinámicos. Use un recurso dinámico si quiere que la métrica de parámetros se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático.  
  
> [!NOTE]
>  Los recursos dinámicos tienen la palabra clave *clave* anexado al nombre de propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso y usar los recursos dinámicos de parámetros del sistema para aplicar estilo a un botón o personalizarlo. Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en el ejemplo se cambia el tamaño de un botón mediante la asignación de <xref:System.Windows.SystemParameters> valores al alto y ancho del botón.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>Vea también  
 [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Usar SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [Usar SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
