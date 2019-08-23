---
title: Procedimiento Usar claves de parámetros del sistema
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: edacb4b98ab01f081f668dc3374f6588492210d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918370"
---
# <a name="how-to-use-system-parameters-keys"></a>Procedimiento Usar claves de parámetros del sistema
Los recursos del sistema exponen varias métricas del sistema como recursos para ayudar a los desarrolladores a crear efectos visuales coherentes con la configuración del sistema. <xref:System.Windows.SystemParameters>es una clase que contiene los valores de parámetro del sistema y las claves de recursos que se enlazan a <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> los <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>valores, por ejemplo, y. Las métricas de parámetros del sistema se pueden usar como recursos estáticos o dinámicos. Use un recurso dinámico si quiere que la métrica de parámetros se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático.  
  
> [!NOTE]
> Los recursos dinámicos tienen la palabra *clave* keyword anexada al nombre de la propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso y usar los recursos dinámicos de parámetros del sistema para aplicar estilo a un botón o personalizarlo. En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] este ejemplo se ajusta el tamaño de un <xref:System.Windows.SystemParameters> botón asignando valores al ancho y alto del botón.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>Vea también

- [Pintar un área con un pincel del sistema](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Usar SystemFonts](how-to-use-systemfonts.md)
- [Usar SystemParameters](how-to-use-systemparameters.md)
