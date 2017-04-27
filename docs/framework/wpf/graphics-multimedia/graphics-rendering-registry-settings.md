---
title: "Configuraci&#243;n del Registro en la representaci&#243;n de gr&#225;ficos | Microsoft Docs"
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
  - "gráficos [WPF], representar"
  - "representar gráficos"
  - "representar gráficos, configuración del Registro"
  - "representar gráficos, solucionar problemas"
  - "solucionar problemas de representación de gráficos"
ms.assetid: f4b41b42-327d-407c-b398-3ed5f505df8b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Configuraci&#243;n del Registro en la representaci&#243;n de gr&#225;ficos
En este tema se proporciona información general sobre la configuración del Registro para la representación de gráficos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que afecta a las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
<a name="overview"></a>   
## Cuándo utilizar los valores del Registro para la representación de gráficos  
 Estos valores del Registro se proporciona con fines de solución de problemas, depuración y soporte técnico.  Dado que los cambios del Registro afectan a todas las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], una aplicación nunca debe modificar las claves del Registro automáticamente ni durante la instalación.  
  
<a name="xpdmandwddm"></a>   
## ¿Qué son XPDM y WDDM?  
 Algunos de los valores del Registro para la representación de gráficos tienen valores predeterminados diferentes, dependiendo de si la tarjeta de vídeo utiliza un controlador XPDM o WDDM.  XPDM es el Modelo de controladores de pantalla de [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] y WDDM es el Modelo de controladores de pantalla de Windows.  WDDM está disponible en los equipos que ejecutan [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] y [!INCLUDE[win7](../../../../includes/win7-md.md)].  XPDM está disponible en los equipos que ejecutan [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)], [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] y [!INCLUDE[TLA#tla_winnetsvrfam](../../../../includes/tlasharptla-winnetsvrfam-md.md)].  Para obtener más información sobre WDDM, vea [Windows Vista Display Driver Model Design Guide](http://go.microsoft.com/fwlink/?LinkId=178394).  
  
<a name="registry_settings"></a>   
## Valores del Registro  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona cuatro valores del Registro para controlar la representación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
|Configuración|Descripción|  
|-------------------|-----------------|  
|**Deshabilitar la opción de aceleración de hardware**|Especifica si la aceleración de hardware debe estar habilitada.|  
|**Valor máximo de muestreo múltiple**|Especifica el grado de muestreo múltiple para el suavizado de contorno del contenido [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].|  
|**Valor de fecha de controlador de vídeo necesario**|Especifica si el sistema deshabilita la aceleración de hardware para los controladores publicados antes de noviembre de 2004.|  
|**Usar la opción de rasterizador de referencia**|Especifica si [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] debe utilizar el rasterizador de referencia.|  
  
 Cualquier utilidad de configuración externa que pueda hacer referencia a los valores del Registro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede tener acceso a estos valores.  Estos valores se pueden crear o modificar también mediante el acceso directo a los valores utilizando el Editor del Registro de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
<a name="disablehardwareacceleration"></a>   
## Deshabilitar la opción de aceleración de hardware  
  
|Clave del Registro|Tipo de valor|  
|------------------------|-------------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\DisableHWAcceleration`|DWORD|  
  
 El valor de **deshabilitar la opción de aceleración de hardware** permite desactivar la aceleración de hardware con fines de depuración y pruebas.  Si se aprecian anomalías de representación en una aplicación, intente desactivar la aceleración de hardware.  Si la anomalía desaparece, puede que el problema se deba al controlador de vídeo.  
  
 **Deshabilitar la opción de aceleración de hardware** es un valor DWORD que puede ser 0 ó 1.  Un valor de 1 deshabilita la aceleración de hardware.  El valor 0 habilita la aceleración de hardware, siempre que el sistema cumpla los requisitos de aceleración de hardware; para obtener más información, consulte [Niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
<a name="maxmultisample"></a>   
## Valor máximo de muestreo múltiple  
  
|Clave del Registro|Tipo de valor|  
|------------------------|-------------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\MaxMultisampleType`|DWORD|  
  
 El **valor máximo de multimuestreo** permite ajustar la cantidad máxima de suavizado de contorno del contenido [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  Use este nivel para deshabilitar el suavizado de contorno de [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] en [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] o habilitarlo en [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].  
  
 El **valor máximo de muestreo múltiple** es un valor DWORD que va de 0 a 16.  El valor 0 especifica que el suavizado de contorno del muestreo múltiple del contenido 3D debe estar deshabilitado, y el valor 16 intentará usar un suavizado de contorno de hasta 16x, si lo admite la tarjeta de vídeo.  Tenga en cuenta que establecer el valor de esta clave del Registro en equipos que usen controladores XPDM hará que las aplicaciones utilicen gran cantidad de memoria de vídeo adicional, disminuirá el rendimiento de la representación [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] y podría dar lugar a errores de representación y a problemas de estabilidad.  
  
 Cuando no se establece esta clave del Registro, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza como valor predeterminado el 0 para los controladores XPDM y el 4 para los controladores WDDM.  
  
<a name="requiredvideodriverdatesetting"></a>   
## Valor de fecha de controlador de vídeo necesario  
  
|Clave del Registro|Tipo de valor|  
|------------------------|-------------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\RequiredVideoDriverDate`|Cadena.|  
  
 En noviembre de 2004, [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] publicó una nueva versión de las directrices de pruebas de controladores; los controladores escritos después de esta fecha ofrecen mayor estabilidad.  De manera predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizará la canalización de aceleración de hardware para estos controladores y recurrirá a la representación de software para los controladores XPDM publicados antes de esta fecha.  
  
 El **valor de fecha de controlador de vídeo necesario** permite especificar una fecha mínima alternativa para los controladores XPDM.  Únicamente debe especificar fechas anteriores a noviembre de 2004 si está seguro de que el controlador de vídeo es lo bastante estable para admitir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 El valor de controlador de vídeo necesario acepta una cadena del formato siguiente:  
  
||  
|-|  
|*AAAA* `/` *MM* `/` *DD*|  
  
 Donde *AAAA* es el año con cuatro dígitos, *MM* es el mes con dos dígitos y *DD* es el día con dos dígitos.  Cuando este valor no se establece, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza noviembre de 2004 como fecha del controlador de vídeo necesaria.  
  
<a name="usereferencerasterizeroption"></a>   
## Usar la opción de rasterizador de referencia  
  
|Clave del Registro|Tipo de valor|  
|------------------------|-------------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\UseReferenceRasterizer`|DWORD|  
  
 El valor de **usar la opción de rasterizador de referencia** permite forzar un modo de representación de hardware simulado en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para la depuración: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entra en el modo de hardware, pero usa el rasterizador de software de referencia [!INCLUDE[TLA#tla_d3d](../../../../includes/tlasharptla-d3d-md.md)], d3dref9.dll, en lugar de un dispositivo de hardware real.  
  
 El rasterizador de referencia es muy lento, pero omite el controlador de vídeo para evitar cualquier problema de representación producido por problemas del controlador.  Por esta razón, puede utilizar el rasterizador de referencia para determinar si el controlador de vídeo es el causante de los problemas de representación.  El archivo d3dref9.dll debe estar en una ubicación donde la aplicación pueda tener acceso a él, como en cualquier ubicación de la ruta de acceso del sistema o en el directorio local de la aplicación.  
  
 El valor de **utilizar la opción de rasterizador de referencia** acepta un valor DWORD.  El valor 0 indica que no se utiliza el rasterizador de referencia.  Cualquier otro valor distinto de cero fuerza a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a utilizar el rasterizador de referencia.  
  
## Vea también  
 [Niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)   
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)