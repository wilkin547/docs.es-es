---
title: "C&#243;mo: Utilizar SystemParameters | Microsoft Docs"
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
  - "clases, SystemParameters"
  - "SystemParameters (clase)"
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# C&#243;mo: Utilizar SystemParameters
En este ejemplo se muestra cómo obtener acceso a las propiedades de <xref:System.Windows.SystemParameters> y utilizarlas para aplicar un estilo a un botón o personalizarlo.  
  
## Ejemplo  
 Los recursos del sistema exponen diversos valores del sistema como recursos, a fin de ayudarle a crear efectos visuales coherentes con la configuración del sistema.  <xref:System.Windows.SystemParameters> es una clase que contiene tanto propiedades de los valores de los parámetros del sistema como claves de recurso que se enlazan a los valores.  Por ejemplo, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> es un valor de propiedad <xref:System.Windows.SystemParameters> y <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> es la clave de recurso correspondiente.  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede utilizar los miembros de <xref:System.Windows.SystemParameters> como propiedades estáticas o como referencias de recurso dinámicas \(donde se use como clave el valor de propiedad estática\).  Utilice una referencia dinámica a un recurso si desea que el valor del sistema se actualice automáticamente mientras se ejecuta la aplicación; de lo contrario, utilice una referencia estática.  Las claves de recurso tienen el sufijo `Key` anexado al nombre de propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso a los valores estáticos de <xref:System.Windows.SystemParameters> y utilizarlos para aplicar un estilo a un botón o personalizarlo.  En este de código de marcado de ejemplo se ajusta el tamaño del botón aplicándole valores de <xref:System.Windows.SystemParameters>.  
  
 [!code-xml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 Para utilizar los valores de <xref:System.Windows.SystemParameters> en el código, no tiene que utilizar referencias estáticas o referencias de recurso dinámicas.  En su lugar, utilice los valores de la clase <xref:System.Windows.SystemParameters>.  Aunque en apariencia las propiedades que no son claves se definen como propiedades estáticas, el comportamiento en tiempo de ejecución de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando está hospedado en el sistema hace que se vuelvan a evaluar las propiedades en tiempo real y que se reflejen correctamente los cambios a los valores del sistema controlados por el usuario. En el ejemplo siguiente se muestra cómo establecer el ancho y el alto de un botón mediante los valores de <xref:System.Windows.SystemParameters>.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## Vea también  
 <xref:System.Windows.SystemParameters>   
 [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Utilizar SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)   
 [Utilizar claves de parámetros del sistema](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)