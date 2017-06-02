---
title: "C&#243;mo: Utilizar claves de par&#225;metros del sistema | Microsoft Docs"
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
  - "claves de recursos, SystemParameters (clase)"
  - "SystemParameters (clase)"
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Utilizar claves de par&#225;metros del sistema
Los recursos del sistema exponen diversas métricas del sistema como recursos para ayudar a los desarrolladores a crear efectos visuales coherentes con la configuración del sistema.  <xref:System.Windows.SystemParameters> es una clase que contiene tanto claves de recursos como valores de parámetros del sistema que se enlazan a valores, por ejemplo, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> y <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.  Las métricas de los parámetros del sistema se pueden utilizar como recursos estáticos o dinámicos.  Utilice un recurso dinámico si desea que la métrica del parámetro se actualice automáticamente mientras se ejecuta la aplicación; de lo contrario, utilice un recurso estático.  
  
> [!NOTE]
>  Los recursos dinámicos tienen la palabra clave *Key* anexada al nombre de propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso a recursos dinámicos de parámetros del sistema y utilizarlos para aplicar un estilo a un botón o personalizarlo.  En este ejemplo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se ajusta el tamaño de un botón asignando valores de <xref:System.Windows.SystemParameters> al ancho y alto del botón.  
  
## Ejemplo  
 [!code-xml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## Vea también  
 [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Utilizar SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)   
 [Utilizar SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)