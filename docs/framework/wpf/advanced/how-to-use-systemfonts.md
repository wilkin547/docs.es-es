---
title: "C&#243;mo: Utilizar SystemFonts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "clases, SystemFonts"
  - "fuentes, fuentes del sistema"
  - "fuentes del sistema"
  - "SystemFonts (clase)"
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# C&#243;mo: Utilizar SystemFonts
En este ejemplo se muestra cómo utilizar los recursos estáticos de la clase <xref:System.Windows.SystemFonts> para aplicar un estilo a un botón o personalizarlo.  
  
## Ejemplo  
 Los recursos del sistema exponen diversos valores determinados por el sistema como recursos y propiedades, para ayudarle a crear efectos visuales coherentes con la configuración del sistema.  <xref:System.Windows.SystemFonts> es una clase que contiene valores de fuentes del sistema como propiedades estáticas y también propiedades que hacen referencia a las claves de recurso que pueden utilizarse para tener acceso dinámicamente a esos valores en tiempo de ejecución.  Por ejemplo, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> es un valor <xref:System.Windows.SystemFonts> y <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> es su clave de recurso correspondiente.  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede utilizar los miembros de <xref:System.Windows.SystemFonts> como propiedades estáticas o como referencias dinámicas a recursos \(donde se use como clave el valor de propiedad estática\).  Utilice una referencia dinámica a un recurso si desea que la métrica de la fuente se actualice automáticamente mientras se ejecuta la aplicación; de lo contrario, utilice una referencia estática al valor.  
  
> [!NOTE]
>  Las claves de recurso tienen el sufijo "Key" anexado al nombre de propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso a las propiedades de <xref:System.Windows.SystemFonts> como valores estáticos y utilizarlas para aplicar un estilo a un botón o personalizarlo.  En este ejemplo de marcado se asignan los valores de <xref:System.Windows.SystemFonts> a un botón.  
  
 [!code-xml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Para utilizar los valores de <xref:System.Windows.SystemFonts> en el código, no tiene que utilizar un valor estático o una referencia de recurso dinámica.  En lugar de ello, utilice las propiedades que no son claves de la clase <xref:System.Windows.SystemFonts>.  Aunque en apariencia las propiedades que no son claves se definen como propiedades estáticas, el comportamiento en tiempo de ejecución de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando está hospedado en el sistema hace que se vuelvan a evaluar las propiedades en tiempo real y que se reflejen correctamente los cambios a los valores del sistema controlados por el usuario.  En el ejemplo siguiente se muestra cómo especificar la configuración de las fuentes de un botón.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## Vea también  
 <xref:System.Windows.SystemFonts>   
 [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Utilizar SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)   
 [Usar claves de fuentes del sistema](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)   
 [Extensiones de marcado x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md)   
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)