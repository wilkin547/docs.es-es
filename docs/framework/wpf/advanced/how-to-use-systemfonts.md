---
title: Procedimiento Usar SystemFonts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 7438705a82faee464649b5f6f577627a379e9a8c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918363"
---
# <a name="how-to-use-systemfonts"></a>Procedimiento Usar SystemFonts
En este ejemplo se muestra cómo usar los recursos estáticos <xref:System.Windows.SystemFonts> de la clase para aplicar estilo a un botón o personalizarlo.  
  
## <a name="example"></a>Ejemplo  
 Los recursos del sistema exponen varios valores determinados en el sistema como recursos y propiedades para ayudarle a crear objetos visuales coherentes con la configuración del sistema. <xref:System.Windows.SystemFonts>es una clase que contiene ambos valores de fuente del sistema como propiedades estáticas y propiedades que hacen referencia a las claves de recursos que se pueden utilizar para tener acceso a esos valores dinámicamente en tiempo de ejecución. Por ejemplo, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> es un <xref:System.Windows.SystemFonts> valor y <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> es una clave de recurso correspondiente.  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede usar los miembros de como <xref:System.Windows.SystemFonts> propiedades estáticas o referencias de recursos dinámicos (con el valor de la propiedad estática como clave). Use una referencia de recursos dinámicos si quiere que la métrica de fuente se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use una referencia de valor estático.  
  
> [!NOTE]
> Las claves de recurso tienen el sufijo "Key" anexado al nombre de la propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso y usar las <xref:System.Windows.SystemFonts> propiedades de como valores estáticos para aplicar estilo a un botón o personalizarlo. Este ejemplo de marcado asigna <xref:System.Windows.SystemFonts> valores a un botón.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Para usar los valores de <xref:System.Windows.SystemFonts> en el código, no tiene que usar un valor estático o una referencia de recursos dinámicos. En su lugar, use las propiedades que no son de <xref:System.Windows.SystemFonts> clave de la clase. Aunque las propiedades que no son de clave aparentemente se definen como propiedades estáticas, el comportamiento en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiempo de ejecución de tal como lo hospeda el sistema volverá a evaluar las propiedades en tiempo real y tendrá en cuenta correctamente los cambios realizados por el usuario en los valores del sistema. En el ejemplo siguiente se muestra cómo especificar la configuración de fuente de un botón.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.SystemFonts>
- [Pintar un área con un pincel del sistema](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Usar SystemParameters](how-to-use-systemparameters.md)
- [Usar claves de fuentes del sistema](how-to-use-system-fonts-keys.md)
- [Temas "Cómo..."](resources-how-to-topics.md)
- [Extensiones de marcado x:Static](../../xaml-services/x-static-markup-extension.md)
- [Recursos XAML](xaml-resources.md)
- [DynamicResource (extensión de marcado)](dynamicresource-markup-extension.md)
