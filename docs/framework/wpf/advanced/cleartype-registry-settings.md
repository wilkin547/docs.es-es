---
title: Configuración del Registro de ClearType
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: 8f1c4415a834f7eb7c3048a89ab81de6921b7bf6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629942"
---
# <a name="cleartype-registry-settings"></a>Configuración del Registro de ClearType
En este tema se proporciona información general sobre la configuración del registro de ClearType de Microsoft que usan las aplicaciones de WPF.  

<a name="overview"></a>   
## <a name="technology-overview"></a>Información general sobre la tecnología  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]las aplicaciones que representan texto en un dispositivo de pantalla usan las características de ClearType para proporcionar una experiencia de lectura mejorada. ClearType es una tecnología de software desarrollada [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] por que mejora la legibilidad del texto en pantallas de cristal líquido (LCD) existentes, como pantallas de equipos portátiles, pantallas de Pocket PC y monitores de pantalla plana. ClearType funciona mediante el acceso a los elementos de franjas de color vertical individuales en cada píxel de una pantalla LCD. Para obtener más información sobre ClearType, consulte [información general sobre ClearType](cleartype-overview.md).  
  
 El texto que se representa con ClearType puede ser significativamente diferente cuando se ve en varios dispositivos de pantalla. Por ejemplo, un pequeño número de monitores implementa los elementos de franjas de color en orden azul, verde, rojo en lugar del orden rojo, verde, azul [!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]() más común.  
  
 El texto que se representa con ClearType también puede ser significativamente diferente cuando lo ven usuarios con distintos niveles de sensibilidad de color. Algunas personas pueden detectar pequeñas variaciones de color mejor que otras.  
  
 En cada uno de estos casos, es necesario modificar las características de ClearType para proporcionar la mejor experiencia de lectura para cada individuo.  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a>Configuración de registro  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]especifica cuatro valores del registro para controlar las características de ClearType:  
  
|Parámetro|DESCRIPCIÓN|  
|-------------|-----------------|  
|Nivel de ClearType|Describe el nivel de claridad de color de ClearType.|  
|Nivel de gamma|Describe el nivel del componente de color de píxel de una pantalla.|  
|Estructura de píxeles|Describe la distribución de píxeles de una pantalla.|  
|Nivel de contraste del texto|Describe el nivel de contraste del texto que se muestra.|  
  
 Se puede tener acceso a esta configuración mediante una utilidad de configuración externa que sabe cómo hacer referencia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]a la configuración del registro de ClearType identificada. Estos valores de configuración también pueden crearse o modificarse mediante el acceso a los valores directamente a través del Editor del Registro de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 Si no [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]se establece la configuración del registro ClearType (que es el estado predeterminado), [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la aplicación consulta [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] la información de parámetros del sistema para la configuración de suavizado de fuentes.  
  
> [!NOTE]
>  Para obtener información sobre cómo enumerar los nombres de los `SystemParametersInfo` dispositivos de pantalla, consulte la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] función.  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a>Nivel de ClearType  
 El nivel ClearType permite ajustar la representación de texto en función de la sensibilidad y la percepción del color de un individuo. En el caso de algunas personas, la representación del texto que usa ClearType en su nivel más alto no produce la mejor experiencia de lectura.  
  
 El nivel ClearType es un valor entero comprendido entre 0 y 100. El nivel predeterminado es 100, lo que significa que ClearType usa la capacidad máxima de los elementos de franjas de color del dispositivo de pantalla. Sin embargo, un nivel de ClearType de 0 representa el texto en forma de escala de grises. Al establecer el nivel de ClearType entre 0 y 100, puede crear un nivel intermedio que sea adecuado para la sensibilidad del color de un individuo.  
  
### <a name="registry-setting"></a>Configuración del Registro  
 La ubicación de la configuración del registro para el nivel ClearType es una configuración de usuario individual que corresponde a un nombre de dispositivo de pantalla específico:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo de visualización de un usuario `ClearTypeLevel` , se define un valor DWORD. En la captura de pantalla siguiente se muestra la configuración del editor del registro para el nivel ClearType.  
  
 ![Configuración de ClearType en el editor del registro.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]las aplicaciones representan texto en uno de estos dos modos, con y sin ClearType. Cuando el texto se representa sin ClearType, se conoce como representación de escala de grises.  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a>Nivel de gamma  
 El nivel de gamma hace referencia a la relación no lineal entre un valor de píxel y la luminancia. El valor de nivel de gamma debe corresponder a las características físicas de la pantalla; de lo contrario, pueden producirse distorsiones en la salida representada. Por ejemplo, la prueba pueda parecer demasiado ancha o demasiado estrecha, o bien pueden aparecer franjas de color en los bordes de las bandas verticales de los glifos.  
  
 El nivel de gamma es un valor entero comprendido entre 1000 y 2200. El nivel predeterminado es 1900.  
  
### <a name="registry-setting"></a>Configuración del Registro  
 La ubicación de la configuración del Registro para el nivel de gamma es una configuración de equipo local que corresponde a un nombre de pantalla específico:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo de visualización de un usuario `GammaLevel` , se define un valor DWORD. La captura de pantalla siguiente muestra la configuración del Editor del Registro para el nivel de gamma.  
  
 ![Configuración de nivel gamma de ClearType en el editor del registro](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a>Estructura de píxeles  
 La estructura de píxeles describe el tipo de píxeles que componen una pantalla. La estructura de píxeles se define como uno de estos tres tipos:  
  
|Type|Valor|DESCRIPCIÓN|  
|----------|-----------|-----------------|  
|Plano|0|La pantalla no tiene ninguna estructura de píxeles. Esto significa que los orígenes de la luz de cada color se expanden por igual en el área de píxeles, lo que se conoce como representación en escala de grises. Así es como funciona una pantalla estándar. ClearType nunca se aplica al texto representado.|  
|RGB|1|La pantalla tiene píxeles que se componen de tres franjas en el orden siguiente: rojo, verde y azul. ClearType se aplica al texto representado.|  
|BGR|2|La pantalla tiene píxeles que se componen de tres franjas en el orden siguiente: azul, verde y rojo. ClearType se aplica al texto representado. Observe cómo se invierte el orden del tipo RGB.|  
  
 La estructura de píxeles corresponde a un valor entero comprendido entre 0 y 2. El nivel predeterminado es 0, que representa una estructura de píxeles plana.  
  
> [!NOTE]
>  Para obtener información sobre cómo enumerar los nombres de los `EnumDisplayDevices` dispositivos de pantalla, consulte la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] función.  
  
### <a name="registry-setting"></a>Configuración del Registro  
 La ubicación de la configuración del Registro para la estructura de píxeles es una configuración de equipo local que corresponde a un nombre de pantalla específico:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo de visualización de un usuario `PixelStructure` , se define un valor DWORD. La captura de pantalla siguiente muestra la configuración del Editor del Registro para la estructura de píxeles.  
  
 ![Configuración de nivel gamma de ClearType en el editor del registro](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a>Nivel de contraste del texto  
 El nivel de contraste del texto permite ajustar la representación de texto en función de los anchos de las franjas de los glifos. El nivel de contraste del texto es un valor entero comprendido entre 0 y 6: cuanto mayor sea el valor entero, más ancha será la franja. El nivel predeterminado es 1.  
  
### <a name="registry-setting"></a>Configuración del Registro  
 La ubicación de la configuración del Registro para el nivel de contraste del texto es una configuración de usuario individual que corresponde a un nombre de pantalla específico:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo de visualización de un usuario `TextContrastLevel` , se define un valor DWORD. La captura de pantalla siguiente muestra la configuración del Editor del Registro para el nivel de contraste del texto.  
  
 ![Configuración de ClearType en el editor del registro.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>Vea también

- [Información general sobre ClearType](cleartype-overview.md)
- [Suavizado de contorno de ClearType](/windows/desktop/gdi/cleartype-antialiasing)
