---
title: Procedimiento Utilizar claves de parámetros del sistema
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: a71551c5d539d7009fb9a052c81928a009fc4c35
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357201"
---
# <a name="how-to-use-system-parameters-keys"></a>Filtrar Utilizar claves de parámetros del sistema
Los recursos del sistema exponen varias métricas del sistema como recursos para ayudar a los desarrolladores a crear efectos visuales coherentes con la configuración del sistema. <xref:System.Windows.SystemParameters> es una clase que contiene los valores de parámetro del sistema y las claves de recurso que se enlazan a los valores, por ejemplo, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> y <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>. Las métricas de parámetros del sistema se pueden usar como recursos estáticos o dinámicos. Use un recurso dinámico si quiere que la métrica de parámetros se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático.  
  
> [!NOTE]
>  Los recursos dinámicos tienen la palabra clave *clave* anexado al nombre de propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso y usar los recursos dinámicos de parámetros del sistema para aplicar estilo a un botón o personalizarlo. Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en el ejemplo se cambia el tamaño de un botón mediante la asignación <xref:System.Windows.SystemParameters> valores al alto y ancho del botón.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>Vea también
- [Pintar un área con un pincel del sistema](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Usar SystemFonts](how-to-use-systemfonts.md)
- [Usar SystemParameters](how-to-use-systemparameters.md)
