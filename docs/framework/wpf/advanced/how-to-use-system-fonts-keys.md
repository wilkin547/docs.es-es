---
title: "C&#243;mo: Usar claves de fuentes del sistema | Microsoft Docs"
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
  - "claves de recursos, SystemFonts (clase)"
  - "SystemFonts (clase)"
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Usar claves de fuentes del sistema
Los recursos del sistema exponen diversas métricas del sistema como recursos para ayudar a los desarrolladores a crear efectos visuales coherentes con la configuración del sistema.  <xref:System.Windows.SystemFonts> es una clase que contiene tanto valores de fuentes del sistema como recursos de fuentes del sistema enlazados a los valores, por ejemplo <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> y <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.  
  
 Las medidas de las fuentes del sistema se pueden utilizar como recursos estáticos o dinámicos.  Utilice un recurso dinámico si desea que la medida de la fuente se actualice automáticamente mientras se ejecuta la aplicación; de lo contrario, utilice un recurso estático.  
  
> [!NOTE]
>  Los recursos dinámicos tienen la palabra clave *Key* anexada al nombre de propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso a recursos dinámicos de fuentes del sistema y utilizarlos para aplicar un estilo a un botón o personalizarlo.  Este ejemplo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] crea un estilo de botón que asigna los valores <xref:System.Windows.SystemFonts> a un botón.  
  
## Ejemplo  
 [!code-xml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## Vea también  
 [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Utilizar SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)   
 [Utilizar SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)