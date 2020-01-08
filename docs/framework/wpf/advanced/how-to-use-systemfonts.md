---
title: 'Cómo: Utilizar SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 157565ceb9057049aef8b2bf274847d58c6b8dc8
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559968"
---
# <a name="how-to-use-systemfonts"></a>Cómo: Utilizar SystemFonts
En este ejemplo se muestra cómo usar los recursos estáticos de la clase <xref:System.Windows.SystemFonts> para aplicar estilo a un botón o personalizarlo.  
  
## <a name="example"></a>Ejemplo  
 Los recursos del sistema exponen varios valores determinados en el sistema como recursos y propiedades para ayudarle a crear objetos visuales coherentes con la configuración del sistema. <xref:System.Windows.SystemFonts> es una clase que contiene ambos valores de fuente del sistema como propiedades estáticas y propiedades que hacen referencia a las claves de recursos que se pueden utilizar para tener acceso a esos valores dinámicamente en tiempo de ejecución. Por ejemplo, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> es un valor <xref:System.Windows.SystemFonts> y <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> es una clave de recurso correspondiente.  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede usar los miembros de <xref:System.Windows.SystemFonts> como propiedades estáticas o referencias de recursos dinámicos (con el valor de la propiedad estática como clave). Use una referencia de recursos dinámicos si quiere que la métrica de fuente se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use una referencia de valor estático.  
  
> [!NOTE]
> Las claves de recurso tienen el sufijo "Key" anexado al nombre de la propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso y usar las propiedades de <xref:System.Windows.SystemFonts> como valores estáticos para aplicar estilo a un botón o personalizarlo. Este ejemplo de marcado asigna <xref:System.Windows.SystemFonts> valores a un botón.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Para usar los valores de <xref:System.Windows.SystemFonts> en el código, no tiene que usar un valor estático o una referencia de recursos dinámicos. En su lugar, use las propiedades que no son de clave de la clase <xref:System.Windows.SystemFonts>. Aunque las propiedades que no son de clave aparentemente se definen como propiedades estáticas, el comportamiento en tiempo de ejecución de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tal y como se hospeda en el sistema volverá a evaluar las propiedades en tiempo real y tendrá en cuenta correctamente los cambios realizados por el usuario en los valores del sistema. En el ejemplo siguiente se muestra cómo especificar la configuración de fuente de un botón.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.SystemFonts>
- [Pintar un área con un pincel del sistema](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Usar SystemParameters](how-to-use-systemparameters.md)
- [Usar claves de fuentes del sistema](how-to-use-system-fonts-keys.md)
- [Temas "Cómo..."](resources-how-to-topics.md)
- [Extensiones de marcado x:Static](../../../desktop-wpf/xaml-services/xstatic-markup-extension.md)
- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Extensión de marcado DynamicResource](dynamicresource-markup-extension.md)
