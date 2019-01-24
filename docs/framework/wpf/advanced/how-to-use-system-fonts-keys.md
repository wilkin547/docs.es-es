---
title: Procedimiento Usar claves de fuentes del sistema
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: aec3ba8b84836d068b7efcfe53b34b126334b8de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628713"
---
# <a name="how-to-use-system-fonts-keys"></a>Procedimiento Usar claves de fuentes del sistema
Los recursos del sistema exponen varias métricas del sistema como recursos para ayudar a los desarrolladores a crear efectos visuales coherentes con la configuración del sistema. <xref:System.Windows.SystemFonts> es una clase que contiene los valores de fuente del sistema y los recursos de fuentes del sistema que se enlazan a los valores, por ejemplo, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> y <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.  
  
 La métricas de fuentes del sistema se pueden usar como recursos estáticos o dinámicos. Use un recurso dinámico si quiere que la métrica de fuentes se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático.  
  
> [!NOTE]
>  Los recursos dinámicos tienen la palabra clave *clave* anexado al nombre de propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso y usar los recursos dinámicos de fuentes del sistema para aplicar estilo a un botón o personalizarlo. Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en el ejemplo se crea un estilo de botón que asigna <xref:System.Windows.SystemFonts> valores a un botón.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>Vea también
- [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Usar SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
- [Usar SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
