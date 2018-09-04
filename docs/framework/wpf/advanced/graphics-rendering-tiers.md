---
title: Niveles de representación de gráficos
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], performance
- rendering graphics [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
ms.assetid: 08dd1606-02a2-4122-9351-c0afd2ec3a70
ms.openlocfilehash: 9fb24e13ab684170baf5ac3001d3a2d4bcd6df7e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563269"
---
# <a name="graphics-rendering-tiers"></a>Niveles de representación de gráficos
Un nivel de representación define un nivel de funcionalidad y rendimiento de hardware gráfico para un dispositivo que ejecuta un aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  

  
<a name="graphics_hardware"></a>   
## <a name="graphics-hardware"></a>Hardware gráfico  
 Las características del hardware gráfico que más afectan a los niveles de representación son:  
  
-   **RAM de vídeo** La cantidad de memoria de vídeo en el hardware gráfico determina el tamaño y el número de búferes que puede utilizarse para la composición de gráficos.  
  
-   **Sombreador de píxeles** Un sombreador de píxeles es una función de procesamiento de gráficos que calcula los efectos píxel por píxel. Según la resolución de los gráficos mostrados, puede haber varios millones de píxeles que deban procesarse en cada fotograma mostrado.  
  
-   **Sombreador de vértices** Un sombreador de vértices es una función de procesamiento de gráficos que realiza operaciones matemáticas en los datos de vértice del objeto.  
  
-   **Compatibilidad con texturas múltiples** La compatibilidad con texturas múltiples hace referencia a la capacidad de aplicar dos o más texturas distintas durante una operación de combinación en un objeto gráfico 3D. El grado de compatibilidad con texturas múltiples queda determinado por el número de unidades de múltiples texturas en el hardware gráfico.  
  
<a name="rendering_tier_definitions"></a>   
## <a name="rendering-tier-definitions"></a>Definiciones de niveles de representación  
 Las características del hardware gráfico determinan la capacidad de representación de una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El sistema [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define tres niveles de representación:  
  
-   **Nivel de representación 0** Sin aceleración de hardware gráfico. Todas las características de gráficos utilizan la aceleración de software. El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es mayor que la versión 9.0.  
  
-   **Nivel de representación 1** Algunas características de gráficos utilizan la aceleración de hardware gráfico. El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es mayor o igual que la versión 9.0.  
  
-   **Nivel de representación 2** La mayoría de las características de gráficos utiliza la aceleración de hardware gráfico. El nivel de versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es mayor o igual que la versión 9.0.  
  
 El <xref:System.Windows.Media.RenderCapability.Tier%2A?displayProperty=nameWithType> propiedad le permite recuperar el nivel de representación en tiempo de ejecución de la aplicación. El nivel de representación se utiliza para determinar si el dispositivo admite ciertas características de aceleración de gráficos mediante hardware. La aplicación puede emprender diferentes rutas de código en tiempo de ejecución según el nivel de representación que admita el dispositivo.  
  
### <a name="rendering-tier-0"></a>Nivel de representación 0  
 Un valor de nivel de representación de 0 significa que no hay ninguna aceleración de gráficos mediante hardware disponible para la aplicación en el dispositivo. En este nivel del sistema, debe suponer que todos los gráficos se representarán mediante software sin aceleración de hardware. La funcionalidad de este nivel corresponde a una versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] que es menor que 9.0.  
  
### <a name="rendering-tier-1-and-rendering-tier-2"></a>Nivel de representación 1 y nivel de representación 2  
  
> [!NOTE]
>  A partir de .NET Framework 4, el nivel de representación 1 se ha redefinido para incluir solo el hardware gráfico que admite [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 9.0 o posterior. El hardware gráfico que admite [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 7 u 8 ahora se define como el nivel de representación 0.  
  
 Un valor de nivel de representación de 1 o 2 significa que la mayoría de las características gráficas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizará la aceleración de hardware si los recursos necesarios del sistema están disponibles y no se han agotado. Esto corresponde a una versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] que es mayor o igual que 9.0.  
  
 En la tabla siguiente se muestra las diferencias en los gráficos de los requisitos de hardware para el nivel de representación 1 y 2 de nivel de representación:  
  
|Característica|Nivel 1|Nivel 2|  
|-------------|------------|------------|  
|Versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]|Debe ser mayor o igual que 9.0.|Debe ser mayor o igual que 9.0.|  
|RAM de vídeo|Debe ser mayor o igual que 60MB.|Debe ser mayor o igual a 120MB.|  
|Sombreador de píxeles|Nivel de versión debe ser mayor o igual a 2.0.|Nivel de versión debe ser mayor o igual a 2.0.|  
|Sombreador de vértices|Ningún requisito.|Nivel de versión debe ser mayor o igual a 2.0.|  
|Unidades de múltiples texturas|Ningún requisito.|El número de unidades debe ser mayor o igual que 4.|  
  
 Las siguientes características y funcionalidades se aceleran mediante hardware para el nivel de representación 1 y el nivel de representación 2:  
  
|Característica|Notas|  
|-------------|-----------|  
|Representación 2D|Se admite la mayoría de la representación 2D.|  
|Rasterización 3D|Se admite la mayoría de la rasterización 3D.|  
|Filtrado anisotrópico 3D|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] intenta utilizar el filtrado anisotrópico al representar contenido 3D. El filtrado anisotrópico se refiere a la mejora de la calidad de imagen de las texturas en superficies que están lejos y significativamente en ángulo con respecto a la cámara.|  
|Asignación MIP para 3D|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] intenta utilizar la asignación MIP al representar contenido 3D. La asignación MIP mejora la calidad de representación de las texturas cuando una textura ocupa un campo de vista más pequeño en un <xref:System.Windows.Controls.Viewport3D>.|  
|Degradados radiales|Aunque se admiten, evite el uso de <xref:System.Windows.Media.RadialGradientBrush> en objetos grandes.|  
|Cálculos de iluminación 3D|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] realiza la iluminación por vértices, lo que significa que debe calcularse una intensidad de luz en cada vértice para cada material aplicado a una malla.|  
|Representación de texto|La representación de fuentes por debajo del nivel de píxel utiliza sombreadores de píxeles disponibles en el hardware gráfico.|  
  
 Las siguientes características y funcionalidades se aceleran mediante hardware para el nivel de representación 2 únicamente:  
  
|Característica|Notas|  
|-------------|-----------|  
|Suavizado de contorno 3D|El suavizado de contorno 3D solo se admite en sistemas operativos que admiten Windows Display Driver Model (WDDM), como [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] y [!INCLUDE[win7](../../../../includes/win7-md.md)].|  
  
 Las siguientes características y funcionalidades **no** se aceleran mediante hardware :  
  
|Característica|Notas|  
|-------------|-----------|  
|Contenido impreso|Todo el contenido impreso se representa utilizando la canalización de software [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Contenido rasterizado que utiliza <xref:System.Windows.Media.Imaging.RenderTargetBitmap>|Cualquier contenido representado mediante el <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> método <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.|  
|Contenido en mosaico que usa <xref:System.Windows.Media.TileBrush>|Mosaico contenido en el que el <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad de la <xref:System.Windows.Media.TileBrush> está establecido en <xref:System.Windows.Media.TileMode.Tile>.|  
|Superficies que superan el tamaño máximo de textura del hardware gráfico|Para la mayoría del hardware gráfico, las superficies grandes tienen un tamaño de 2048 × 2048 o 4096 × 4096 píxeles.|  
|Cualquier operación cuyos requisitos de RAM de vídeo superen la memoria del hardware gráfico|Puede supervisar el uso de RAM de vídeo de las aplicaciones mediante la herramienta Perforator que se incluye en [WPF Performance Suite](https://msdn.microsoft.com/library/67cafaad-57ad-4ecb-9c08-57fac144393e) en el SDK de Windows.|  
|Ventanas superpuestas|Las ventanas superpuestas permiten que las aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] representen contenido en la pantalla en una ventana no rectangular. En los sistemas operativos que admiten Windows Display Driver Model (WDDM), como [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] y [!INCLUDE[win7](../../../../includes/win7-md.md)], las ventanas superpuestas se aceleran mediante hardware. En otros sistemas, como [!INCLUDE[winxp](../../../../includes/winxp-md.md)], las ventanas superpuestas se representan con software, sin aceleración de hardware.<br /><br /> Puede permitir que las ventanas superpuestas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] estableciendo lo siguiente <xref:System.Windows.Window> propiedades:<br /><br /> -   <xref:System.Windows.Window.WindowStyle%2A> = <xref:System.Windows.WindowStyle.None><br />-   <xref:System.Windows.Window.AllowsTransparency%2A> = `true`<br />-   <xref:System.Windows.Controls.Control.Background%2A> = <xref:System.Windows.Media.Brushes.Transparent%2A>|  
  
<a name="other_resources"></a>   
## <a name="other-resources"></a>Otros recursos  
 Los siguientes recursos pueden ayudarle a analizar las características de rendimiento de su aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="graphics-rendering-registry-settings"></a>Configuración del Registro en la representación de gráficos  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona cuatro valores de configuración del Registro para controlar la representación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
|Parámetro|Descripción|  
|-------------|-----------------|  
|**Opción de deshabilitación de aceleración de hardware**|Especifica si se debe habilitar la aceleración de hardware.|  
|**Valor máximo de muestreo múltiple**|Especifica el grado de muestreo múltiple para el suavizado de contorno del contenido [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].|  
|**Configuración obligatoria de fecha del controlador de vídeo**|Especifica si el sistema deshabilita la aceleración de hardware para los controladores publicados antes de noviembre de 2004.|  
|**Opción de uso del rasterizador de referencia**|Especifica si [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] debe utilizar el rasterizador de referencia.|  
  
 Es posible acceder a estos parámetros mediante una utilidad de configuración externa que pueda hacer referencia a la configuración del Registro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Estos valores de configuración también pueden crearse o modificarse mediante el acceso a los valores directamente a través del Editor del Registro de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. Para obtener más información, consulte [Configuración del Registro en la representación de gráficos](../../../../docs/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings.md).  
  
### <a name="wpf-performance-profiling-tools"></a>Herramientas de generación de perfiles de rendimiento para WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece un conjunto de herramientas de generación de perfiles de rendimiento que le permiten analizar el comportamiento en tiempo de ejecución de la aplicación y determinar los tipos de optimizaciones de rendimiento que puede aplicar. En la tabla siguiente se muestran las herramientas de generación de perfiles de rendimiento que se incluyen en la herramienta de [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)], WPF Performance Suite:  
  
|Herramienta|Descripción|  
|----------|-----------------|  
|Perforator|Se utiliza para analizar el comportamiento de representación.|  
|Visual Profiler|Se utiliza para la generación de perfiles de uso de los servicios de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], tales como el diseño y el control de eventos, mediante elementos del árbol visual.|  
  
 WPF Performance Suite proporciona una vista gráfica enriquecida de los datos de rendimiento. Para obtener más información acerca de las herramientas de rendimiento de WPF, consulte [WPF Performance Suite](https://msdn.microsoft.com/library/67cafaad-57ad-4ecb-9c08-57fac144393e).  
  
### <a name="directx-diagnostic-tool"></a>Herramienta de diagnóstico de DirectX  
 La Herramienta de diagnóstico de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], Dxdiag.exe, está diseñada para ayudarle a solucionar problemas relacionados con [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]. La carpeta predeterminada de instalación para la Herramienta de diagnóstico de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] es:  
  
 `~\Windows\System32`  
  
 Al ejecutar la Herramienta de diagnóstico de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], la ventana principal contiene un conjunto de pestañas que permiten mostrar y diagnosticar información relacionada con [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]. Por ejemplo, la pestaña **Sistema** proporciona información del sistema acerca del equipo y especifica la versión de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] que está instalada en el equipo.  
  
 ![Captura de pantalla: Herramienta de diagnóstico de DirectX](../../../../docs/framework/wpf/advanced/media/directxdiagnostictool-01.png "DirectXDiagnosticTool_01")  
Ventana principal de la Herramienta de diagnóstico de DirectX  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.RenderCapability>  
 <xref:System.Windows.Media.RenderOptions>  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [WPF Performance Suite](https://msdn.microsoft.com/library/67cafaad-57ad-4ecb-9c08-57fac144393e)  
 [Configuración del Registro en la representación de gráficos](../../../../docs/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings.md)  
 [Sugerencias y trucos para animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)
