---
title: "Cómo: Utilizar SystemFonts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ce82724a4e9a547b8441628f43621f29eab6307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-systemfonts"></a>Cómo: Utilizar SystemFonts
Este ejemplo muestra cómo utilizar los recursos estáticos de la <xref:System.Windows.SystemFonts> clase para aplicar estilo a un botón o personalizarlo.  
  
## <a name="example"></a>Ejemplo  
 Los recursos del sistema exponen varios valores determinados en el sistema como recursos y propiedades para ayudarle a crear objetos visuales coherentes con la configuración del sistema. <xref:System.Windows.SystemFonts>es una clase que contiene ambos valores de fuente del sistema como propiedades estáticas y las propiedades que hacen referencia a las claves de recursos que pueden utilizarse para tener acceso a esos valores dinámicamente en tiempo de ejecución. Por ejemplo, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> es un <xref:System.Windows.SystemFonts> valor, y <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> es una clave de recurso correspondiente.  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede utilizar los miembros de <xref:System.Windows.SystemFonts> como propiedades estáticas o referencias de recursos dinámicos (con el valor de propiedad estática como la clave). Use una referencia de recursos dinámicos si quiere que la métrica de fuente se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use una referencia de valor estático.  
  
> [!NOTE]
>  Las claves de recurso tienen el sufijo "Key" anexado al nombre de la propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso y utilizar las propiedades de <xref:System.Windows.SystemFonts> como valores estáticos para aplicar estilo a un botón o personalizarlo. Este ejemplo de marcado se asigna <xref:System.Windows.SystemFonts> valores a un botón.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Para usar los valores de <xref:System.Windows.SystemFonts> en el código, no es necesario utilizar un valor estático o una referencia de recurso dinámico. En su lugar, use las propiedades no son de clave de la <xref:System.Windows.SystemFonts> clase. Aunque las propiedades de clave no aparentemente se definen como propiedades estáticas, el comportamiento de tiempo de ejecución de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando está hospedado en el sistema volverá a evaluar las propiedades en tiempo real y que se reflejen correctamente los cambios controlados por el usuario a valores del sistema. En el ejemplo siguiente se muestra cómo especificar la configuración de fuente de un botón.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.SystemFonts>  
 [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Usar SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [Usar claves de fuentes del sistema](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [Extensiones de marcado x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [DynamicResource (extensión de marcado)](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
