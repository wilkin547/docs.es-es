---
title: "Niveles de representaci&#243;n de gr&#225;ficos | Microsoft Docs"
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
  - "niveles de representación de gráficos"
  - "gráficos, rendimiento"
  - "gráficos, niveles de representación"
  - "representar gráficos"
  - "niveles de representación"
ms.assetid: 08dd1606-02a2-4122-9351-c0afd2ec3a70
caps.latest.revision: 44
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 43
---
# Niveles de representaci&#243;n de gr&#225;ficos
Un nivel de representación define un nivel de rendimiento y funcionalidad del hardware gráfico de un dispositivo en el que se ejecuta una aplicación d[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="graphics_hardware"></a>   
## Hardware gráfico  
 Las características del hardware gráfico que más afectan a los niveles de representación son:  
  
-   **RAM de vídeo**: la cantidad de memoria de vídeo en el hardware gráfico determina el tamaño y el número de búferes que se pueden utilizar para la composición de gráficos.  
  
-   **Sombreador de píxeles**: un sombreador de píxeles es una función de procesamiento de gráficos que calcula los efectos por píxel.  Según la resolución de los gráficos mostrados, puede haber varios millones de píxeles que deban procesarse en cada fotograma mostrado.  
  
-   **Sombreador de vértices**: un sombreador de vértices es una función de procesamiento de gráficos que realiza operaciones matemáticas con los datos de los vértices del objeto.  
  
-   **Compatibilidad con texturas múltiples**: la compatibilidad con texturas múltiples hace referencia a la capacidad de aplicar dos o más texturas distintas durante una operación de mezcla en un objeto gráfico 3D.  El grado de compatibilidad con texturas múltiples viene determinado por el número de unidades de textura múltiple en el hardware gráfico.  
  
<a name="rendering_tier_definitions"></a>   
## Representar definiciones de nivel  
 Las características del hardware gráfico determinan la capacidad de representación de una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define tres niveles de representación:  
  
-   **Nivel de representación 0** Sin aceleración de hardware gráfico.  Todas las características de gráficos usan aceleración de software.  El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es inferior a la versión 9.0.  
  
-   **Nivel de representación 1** Algunas de las características de gráficos usan aceleración de hardware gráfico.  El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es mayor o igual a la versión 9.0.  
  
-   **Nivel de representación 2** La mayoría de las características gráficas utilizan la aceleración de hardware gráfico.  El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es mayor o igual a la versión 9.0.  
  
 La propiedad <xref:System.Windows.Media.RenderCapability.Tier%2A?displayProperty=fullName> permite recuperar el nivel de representación en tiempo de ejecución de la aplicación.  Utilice el nivel de representación para determinar si el dispositivo admite ciertas características de aceleración de gráficos por hardware.  La aplicación puede tomar a continuación diferentes rutas de código en tiempo de ejecución en función del nivel de representación que admita el dispositivo.  
  
### Nivel de representación 0  
 Un valor de nivel de representación 0 significa que no hay ninguna aceleración de hardware gráfico disponible para la aplicación en el dispositivo.  En este nivel, debe suponer que el software representará todos los gráficos sin aceleración por hardware.  La funcionalidad de este nivel corresponde a una versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] inferior a la 9.0.  
  
### Nivel de representación 1 y nivel de representación 2  
  
> [!NOTE]
>  A partir de .NET Framework 4, el nivel de representación 1 se ha redefinido para que solo incluya hardware gráfico compatible con [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 9.0 o posterior.  El hardware gráfico compatible con [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 7.0 u 8.0 se define ahora como el nivel de representación 0.  
  
 Un valor de nivel de representación 1 o 2 significa que la mayoría de las características gráficas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizarán la aceleración por hardware, siempre y cuando no se hayan agotado los recursos necesarios del sistema.  Esto corresponde a la versión 9.0 o posterior de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)].  
  
 En la tabla siguiente se muestran las diferencias de los requisitos de hardware gráfico para el nivel de presentación 1 y el nivel de presentación 2:  
  
|Característica|Nivel 1|Nivel 2|  
|--------------------|-------------|-------------|  
|Versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]|Debe ser mayor o igual que 9.0.|Debe ser mayor o igual que 9.0.|  
|RAM de vídeo|Debe ser mayor o igual que 60 MB.|Debe ser mayor o igual a 120 MB.|  
|Sombreador de píxeles|El nivel de versión debe mayor o igual a 2.0.|El nivel de versión debe mayor o igual a 2.0.|  
|Sombreador de vértices|Ningún requisito.|El nivel de versión debe mayor o igual a 2.0.|  
|Unidades de múltiples texturas|Ningún requisito.|El número de unidades debe ser mayor o igual que 4.|  
  
 Las siguientes características y funciones tienen aceleración por hardware para el nivel de presentación 1 y 2:  
  
|Característica|Notas|  
|--------------------|-----------|  
|Representación en 2D|Se admite la mayor parte de la representación en 2D.|  
|Rasterización en 3D|Se admite la mayoría de la rasterización en 3D.|  
|Filtrado anisotrópico en 3D|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] intenta utilizar el filtrado anisotrópico al representar contenido en 3D.  El filtrado anisotrópico hace referencia a la mejora de la calidad de imagen de las texturas en superficies que se encuentran lejos y formando un ángulo agudo respecto a la cámara.|  
|Asignación MIP para 3D|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] intenta utilizar la asignación MIP al representar contenido en 3D. La asignación MIP mejora la calidad de representación de texturas cuando una textura ocupa un campo de visión más pequeño en <xref:System.Windows.Controls.Viewport3D>.|  
|Degradados radiales|Aunque sea compatible, evite el uso de <xref:System.Windows.Media.RadialGradientBrush> en objetos grandes.|  
|Cálculos de iluminación 3D|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] realiza la iluminación por vértices, lo que significa que debe calcularse una intensidad de luz en cada vértice para cada material que se aplique a una malla.|  
|Representación de texto|La representación de fuentes por debajo del nivel de píxel utiliza sombreadores de píxeles disponibles en el hardware gráfico.|  
  
 Las siguientes características y funciones solo tienen aceleración por hardware para el nivel de presentación 2:  
  
|Característica|Notas|  
|--------------------|-----------|  
|Suavizado de contorno 3D|El suavizado de contorno 3D solamente se admite en los sistemas operativos compatibles con el Modelo de controladores de pantalla de Windows \(WDDM\), como [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] y [!INCLUDE[win7](../../../../includes/win7-md.md)].|  
  
 Las siguientes características y funciones **no** tienen aceleración por hardware:  
  
|Característica|Notas|  
|--------------------|-----------|  
|Contenido impreso|Todo el contenido impreso se representa utilizando el conducto de software [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Contenido rasterizado que utiliza <xref:System.Windows.Media.Imaging.RenderTargetBitmap>|Contenido representado usando el método <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> de <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.|  
|Contenido en mosaico que utiliza <xref:System.Windows.Media.TileBrush>|Contenido en mosaico en el que la propiedad <xref:System.Windows.Media.TileBrush.TileMode%2A> de <xref:System.Windows.Media.TileBrush> esté establecida en <xref:System.Windows.Media.TileMode>.|  
|Superficies que superan el tamaño de textura máximo del hardware gráfico|Para la mayoría del hardware gráfico, las superficies grandes tienen un tamaño de 2048x2048 o 4096x4096 píxeles.|  
|Cualquier operación cuyos requisitos de RAM de vídeo superen la memoria del hardware gráfico|Puede supervisar el uso de la RAM de vídeo de la aplicación mediante la herramienta Perforator, que se incluye en [WPF Performance Suite](../Topic/WPF%20Performance%20Suite.md) del SDK de Windows.|  
|Ventanas superpuestas|Las ventanas superpuestas permiten a las aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] representar contenido en la pantalla en una ventana no rectangular.  En los sistemas operativos compatibles con el Modelo de controladores de pantalla de Windows \(WDDM\), como [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] y [!INCLUDE[win7](../../../../includes/win7-md.md)], las ventanas superpuestas se aceleran mediante hardware.  En otros sistemas, tales como [!INCLUDE[winxp](../../../../includes/winxp-md.md)], las ventanas superpuestas se representan mediante software, sin aceleración de hardware.<br /><br /> Puede habilitar las ventanas superpuestas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] estableciendo las siguientes propiedades <xref:System.Windows.Window>:<br /><br /> -   <xref:System.Windows.Window.WindowStyle%2A> \= <xref:System.Windows.WindowStyle><br />-   <xref:System.Windows.Window.AllowsTransparency%2A> \= `true`<br />-   <xref:System.Windows.Controls.Control.Background%2A> \= <xref:System.Windows.Media.Brushes.Transparent%2A>|  
  
<a name="other_resources"></a>   
## Otros recursos  
 Los recursos siguientes pueden ayudarle a analizar las características de rendimiento de la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Configuración del Registro en la representación de gráficos  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona cuatro valores del Registro para controlar la representación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
|Configuración|Descripción|  
|-------------------|-----------------|  
|**Deshabilitar la opción de aceleración de hardware**|Especifica si la aceleración de hardware debe estar habilitada.|  
|**Valor máximo de muestreo múltiple**|Especifica el grado de muestreo múltiple para el suavizado de contorno del contenido [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].|  
|**Valor de fecha de controlador de vídeo necesario**|Especifica si el sistema deshabilita la aceleración de hardware para los controladores publicados antes de noviembre de 2004.|  
|**Usar la opción de rasterizador de referencia**|Especifica si [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] debe utilizar el rasterizador de referencia.|  
  
 Cualquier utilidad de configuración externa que pueda hacer referencia a los valores del Registro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede tener acceso a estos valores.  Estos valores se pueden crear o modificar también mediante el acceso directo a los valores utilizando el Editor del Registro de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  Para obtener más información, vea [Configuración del Registro en la representación de gráficos](../../../../docs/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings.md).  
  
### Herramientas de generación de perfiles de rendimiento para WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un conjunto de herramientas de generación de perfiles de rendimiento que permiten analizar el funcionamiento de la aplicación en tiempo de ejecución y determinar los tipos de optimización de rendimiento que se pueden aplicar.  La tabla siguiente muestra las herramientas de generación de perfiles de rendimiento que se incluyen en la herramienta [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)], WPF Performance Suite:  
  
|Herramienta|Descripción|  
|-----------------|-----------------|  
|Perforator|Se utiliza para analizar el comportamiento de representación.|  
|Visual Profiler|Se utiliza para generar perfiles de uso de servicios [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], tales como el diseño y el control de eventos, mediante elementos del árbol visual.|  
  
 WPF Performance Suite proporciona una vista gráfica completa de los datos de rendimiento.  Para obtener más información sobre las herramientas de rendimiento de WPF, vea [WPF Performance Suite](../Topic/WPF%20Performance%20Suite.md).  
  
### Herramienta de diagnóstico de DirectX  
 La herramienta de diagnóstico de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], Dxdiag.exe, está diseñada para ayudarle a solucionar problemas relacionados con [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)].  La carpeta de instalación predeterminada para la herramienta de diagnóstico de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es:  
  
 `~\Windows\System32`  
  
 Al ejecutar la herramienta de diagnóstico de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], la ventana principal contiene un conjunto de fichas que permiten mostrar y diagnosticar información relacionada con [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)].  Por ejemplo, la ficha **System** proporciona información del sistema sobre el equipo y especifica la versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] que está instalada en el equipo.  
  
 ![Captura de pantalla: Herramienta de diagnóstico DirectX](../../../../docs/framework/wpf/advanced/media/directxdiagnostictool-01.png "DirectXDiagnosticTool\_01")  
Ventana principal de la herramienta de diagnóstico de DirectX  
  
## Vea también  
 <xref:System.Windows.Media.RenderCapability>   
 <xref:System.Windows.Media.RenderOptions>   
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [WPF Performance Suite](../Topic/WPF%20Performance%20Suite.md)   
 [Configuración del Registro en la representación de gráficos](../../../../docs/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings.md)   
 [Sugerencias y trucos para animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)