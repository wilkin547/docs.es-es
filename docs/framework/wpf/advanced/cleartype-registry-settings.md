---
title: "Configuraci&#243;n del Registro de ClearType | Microsoft Docs"
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
  - "ClearType, configuración del Registro"
  - "tipografía, configuración del Registro de ClearType"
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Configuraci&#243;n del Registro de ClearType
En este tema se proporciona información general sobre la configuración del Registro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] utilizada por las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="overview"></a>   
## Información general sobre la tecnología  
 Las aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que presentan texto en un dispositivo de usan utilizan las características de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] para proporcionar una experiencia de lectura mejorada.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] es una tecnología de software desarrollada por [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] que mejora la legibilidad del texto en las pantallas de cristal líquido \(LCD\) existentes, tales como las de los equipos portátiles, los Pocket PC o los monitores de pantalla plana.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] funciona teniendo acceso a los elementos de las bandas de color verticales individuales de cada píxel de una pantalla LCD.  Para obtener más información sobre [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], vea [Información general sobre ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md).  
  
 El texto que se representa con [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] puede presentar diferencias significativas al verlo en los distintos dispositivos de pantalla.  Por ejemplo, algunos monitores implementan los elementos de bandas de color en el orden azul, verde y rojo, en lugar de en el orden más común, rojo, verde y azul \([!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]\).  
  
 El texto representado con [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] también puede resultar muy diferente cuando lo leen personas con diversos niveles de sensibilidad al color.  Algunas personas son capaces de detectar pequeñas variaciones de color mejor que otras.  
  
 En cada uno de estos casos, es preciso modificar las características de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] a fin de proporcionar la mejor experiencia de lectura a cada persona.  
  
<a name="registry_settings"></a>   
## Valores del Registro  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] especifica cuatro valores del Registro para controlar las características de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]:  
  
|Configuración|Descripción|  
|-------------------|-----------------|  
|Nivel de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]|Describe el nivel de claridad del color de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].|  
|Nivel gamma|Describe el nivel del componente de color de píxel para un dispositivo de pantalla.|  
|Estructura de píxeles|Describe la organización de los píxeles para un dispositivo de pantalla.|  
|Nivel de contraste del texto|Describe el nivel de contraste para el texto mostrado.|  
  
 Cualquier utilidad de configuración externa que pueda hacer referencia a los valores del Registro identificados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] puede tener acceso a estos valores.  Estos valores se pueden crear o modificar también mediante el acceso directo a ellos utilizando el Editor del Registro de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 Si los valores del Registro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] no se establecen \(que es el estado predeterminado\), la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consulta los valores de suavizado de fuentes en la información de parámetros de sistema de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
> [!NOTE]
>  Para obtener información sobre cómo enumerar los nombres de los dispositivos de pantalla, vea la función `SystemParametersInfo` de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
<a name="ClearType_level"></a>   
## ClearType Level  
 El nivel de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] permite ajustar la representación de texto basándose en la sensibilidad y percepción del color de una persona. Para algunas personas, la representación de texto que utiliza el máximo nivel de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] no da lugar a la mejor experiencia de lectura.  
  
 El nivel de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] es un valor entero comprendido entre 0 y 100.  El nivel predeterminado es 100, que significa que [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] emplea la máxima capacidad de los elementos de bandas de color del dispositivo de pantalla.  Sin embargo, un nivel de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] de 0 representa el texto en formato de escala de grises.  Estableciendo el nivel de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] en un valor comprendido entre 0 y 100, puede crear un nivel intermedio adecuado para la sensibilidad al color de la persona.  
  
### Valor del Registro  
 La ubicación de valor del Registro correspondiente al nivel de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] es un valor de usuario individual que corresponde al nombre de un dispositivo de pantalla concreto:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo de pantalla de un usuario, se define un valor DWORD de `ClearTypeLevel`.  En la captura de pantalla siguiente se muestra el valor en el Editor del Registro para el nivel de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].  
  
 ![Configuración de ClearType en el Editor del Registro](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
> [!NOTE]
>  Las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] representan el texto en uno de estos dos modos: con y sin [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)].  Cuando el texto se representa sin [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], se denomina representación en escala de grises.  
  
<a name="gamma_level"></a>   
## Nivel gamma  
 El nivel gamma hace referencia a la relación no lineal entre el valor y la luminancia de un píxel.  El valor gamma debe corresponder a las características físicas del dispositivo de pantalla; de lo contrario, la representación puede aparecer distorsionada.  Por ejemplo, el texto puede aparecer demasiado ancho o estrecho, o puede suceder que aparezcan franjas de color en los bordes de las astas de los glifos.  
  
 El nivel gamma es un valor entero comprendido entre 1000 y 2200.  El nivel predeterminado es 1900.  
  
### Valor del Registro  
 La ubicación de valor del Registro correspondiente al nivel gamma es un valor del equipo local que corresponde a un nombre de dispositivo de pantalla concreto:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo de pantalla de un usuario, se define un valor DWORD de `GammaLevel`.  En la captura de pantalla siguiente se muestra el valor en el Editor del Registro para el nivel gamma.  
  
 ![Configuración de ClearType en el Editor del Registro](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="pixel_structure"></a>   
## Estructura de píxeles  
 La estructura de píxeles describe el tipo de píxeles que constituyen un dispositivo de pantalla.  La estructura de píxeles se define como uno de estos tres tipos:  
  
|Tipo|Valor|Descripción|  
|----------|-----------|-----------------|  
|Plana|0|El dispositivo de pantalla no tiene ninguna estructura de píxeles.  Esto significa que las fuentes de iluminación para cada color se expanden por igual sobre el área de píxeles, lo que se denomina representación en escala de grises.  Así es como funciona un dispositivo de pantalla estándar.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] nunca se aplica al texto presentado.|  
|RGB|1|El dispositivo de pantalla tiene píxeles compuestos de tres bandas en el orden siguiente: rojo, verde y azul.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] se aplica al texto presentado.|  
|BGR|2|El dispositivo de pantalla tiene píxeles compuestos de tres bandas en el orden siguiente: azul, verde y rojo.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] se aplica al texto presentado.  Observe que el orden es el contrario que en el tipo RGB.|  
  
 La estructura de píxeles corresponde a un valor entero comprendido entre 0 y 2.  El nivel predeterminado es 0, que representa una estructura de píxeles plana.  
  
> [!NOTE]
>  Para obtener información sobre cómo enumerar los nombres de los dispositivos de pantalla, vea la función `EnumDisplayDevices` de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
### Valor del Registro  
 La ubicación del valor del Registro correspondiente a la estructura de píxeles es un valor del equipo local que corresponde a un nombre de dispositivo de pantalla concreto:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo de pantalla de un usuario, se define un valor DWORD de `PixelStructure`.  En la captura de pantalla siguiente se muestra el valor en el Editor del Registro para la estructura de píxeles.  
  
 ![Configuración de ClearType en el Editor del Registro](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="text_contrast_level"></a>   
## Nivel de contraste del texto  
 El nivel de contraste del texto permite ajustar la representación del texto basándose en el ancho de las astas de los glifos.  El nivel de contraste del texto es un valor entero comprendido entre 0 y 6. Cuanto mayor es el valor entero, más ancho es el asta.  El nivel predeterminado es 1.  
  
### Valor del Registro  
 La ubicación de valor del Registro correspondiente al nivel de contraste del texto es un valor de usuario individual que corresponde al nombre de un dispositivo de pantalla concreto:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo de pantalla de un usuario, se define un valor DWORD de `TextContrastLevel`.  En la captura de pantalla siguiente se muestra el valor en el Editor del Registro para el nivel de contraste del texto.  
  
 ![Configuración de ClearType en el Editor del Registro](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
## Vea también  
 [Información general sobre ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md)   
 [Método de suavizado de contorno ClearType](_win32_ClearType_Antialiasing)