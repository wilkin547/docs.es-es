---
title: "C&#243;mo: Pintar un &#225;rea con un pincel del sistema | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "pinceles, pintar con pinceles del sistema"
  - "dibujar, con pinceles del sistema"
  - "pinceles del sistema, pintar con"
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Pintar un &#225;rea con un pincel del sistema
La clase <xref:System.Windows.SystemColors> proporciona acceso a los pinceles y colores del sistema, tales como <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A> y <xref:System.Windows.SystemColors.DesktopBrush%2A>.  Un pincel del sistema es un objeto <xref:System.Windows.Media.SolidColorBrush> que pinta una área con el color del sistema especificado.  Un pincel del sistema siempre genera un relleno sólido; no se puede utilizar para crear un degradado.  
  
 Puede utilizar los pinceles del sistema como recursos estáticos o dinámicos.  Utilice un recurso dinámico si desea que el pincel se actualice automáticamente en caso de que el usuario cambie el pincel del sistema mientras se ejecuta la aplicación; de lo contrario, utilice un recurso estático.  La clase SystemColors contiene varias propiedades estáticas que cumplen una convención de nomenclatura estricta:  
  
-   *\<SystemColor\>*Brush  
  
     Obtiene una referencia estática a un objeto <xref:System.Windows.Media.SolidColorBrush> del color del sistema especificado.  
  
-   *\<SystemColor\>*BrushKey  
  
     Obtiene una referencia dinámica a un objeto <xref:System.Windows.Media.SolidColorBrush> del color del sistema especificado.  
  
-   *\<SystemColor\>*Color  
  
     Obtiene una referencia estática a una estructura <xref:System.Windows.Media.Color> del color del sistema especificado.  
  
-   *\<SystemColor\>*ColorKey  
  
     Obtiene una referencia dinámica a la estructura <xref:System.Windows.Media.Color> del color del sistema especificado.  
  
 Un color del sistema es una estructura <xref:System.Windows.Media.Color> que se puede utilizar para configurar un pincel.  Por ejemplo, puede crear un degradado con los colores del sistema estableciendo las propiedades <xref:System.Windows.Media.GradientStop.Color%2A> de los puntos de degradado de un objeto <xref:System.Windows.Media.LinearGradientBrush> degradado en colores del sistema.  Para obtener un ejemplo, vea [Usar colores del sistema en un degradado](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza una referencia de pincel del sistema dinámica para establecer el fondo de un botón.  
  
 [!code-xml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 En el ejemplo siguiente se utiliza una referencia de pincel del sistema estática para establecer el fondo de un botón.  
  
 [!code-xml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Para obtener un ejemplo que muestra cómo utilizar un color del sistema en un degradado, vea [Usar colores del sistema en un degradado](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## Vea también  
 [Usar colores del sistema en un degradado](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)   
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)