---
title: Configuración del Registro de ClearType
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: bedd99fcf9b4ca1d10b4c24d7cff9de320e6fd12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186175"
---
# <a name="cleartype-registry-settings"></a>Configuración del Registro de ClearType
En este tema se proporciona información general sobre la configuración del Registro ClearType de Microsoft que usan las aplicaciones WPFWPF.  

<a name="overview"></a>
## <a name="technology-overview"></a>Información general sobre la tecnología  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]las aplicaciones que representan texto en un dispositivo de visualización utilizan las características ClearType para proporcionar una experiencia de lectura mejorada. ClearType es una tecnología de software desarrollada por Microsoft que mejora la legibilidad del texto en pantallas LCD existentes (pantallas de cristal líquido), como pantallas de portátiles, pantallas de Pocket PC y monitores de pantalla plana. ClearType funciona accediendo a los elementos de franjas de color verticales individuales en cada píxel de una pantalla LCD. Para obtener más información sobre ClearType, vea [ClearType Overview](cleartype-overview.md).  
  
 El texto que se representa con ClearType puede parecer significativamente diferente cuando se ve en varios dispositivos de visualización. Por ejemplo, un pequeño número de monitores implementan los elementos de franja de color en orden azul, verde, rojo en lugar del orden rojo, verde, azul (RGB) más común.  
  
 El texto que se representa con ClearType también puede parecer significativamente diferente cuando lo ven personas con diferentes niveles de sensibilidad al color. Algunas personas pueden detectar pequeñas variaciones de color mejor que otras.  
  
 En cada uno de estos casos, ClearType características deben modificarse con el fin de proporcionar la mejor experiencia de lectura para cada individuo.  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a>Configuración de registro  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]especifica cuatro configuraciones del Registro para controlar las características de ClearType:  
  
|Configuración|Descripción|  
|-------------|-----------------|  
|Nivel ClearType|Describe el nivel de claridad de color ClearType.|  
|Nivel de gamma|Describe el nivel del componente de color de píxel de una pantalla.|  
|Estructura de píxeles|Describe la distribución de píxeles de una pantalla.|  
|Nivel de contraste del texto|Describe el nivel de contraste del texto que se muestra.|  
  
 Se puede acceder a esta configuración mediante una utilidad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de configuración externa que sabe cómo hacer referencia a la configuración del Registro ClearType identificada. Esta configuración también se puede crear o modificar accediendo a los valores directamente mediante el Editor del Registro de Windows.  
  
 Si [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no se establece la configuración del Registro ClearType (que es el estado predeterminado), la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación consulta la información de parámetros del sistema de Windows para la configuración de suavizado de fuentes.  
  
> [!NOTE]
> Para obtener información sobre cómo enumerar `SystemParametersInfo`los nombres de dispositivos de visualización, consulte la función Win32.  
  
<a name="ClearType_level"></a>
## <a name="cleartype-level"></a>Nivel de ClearType  
 El nivel ClearType le permite ajustar la representación del texto en función de la sensibilidad del color y la percepción de un individuo. Para algunas personas, la representación de texto que usa ClearType en su nivel más alto no produce la mejor experiencia de lectura.  
  
 El nivel ClearType es un valor entero que oscila entre 0 y 100. El nivel predeterminado es 100, lo que significa que ClearType utiliza la capacidad máxima de los elementos de franja de color del dispositivo de visualización. Sin embargo, un ClearType nivel de 0 representa el texto como escala de grises. Al establecer el nivel ClearType en algún lugar entre 0 y 100, puede crear un nivel intermedio que sea adecuado para la sensibilidad de color de un individuo.  
  
### <a name="registry-setting"></a>Configuración del registro  
 La ubicación de configuración del Registro para el nivel ClearType es una configuración de usuario individual que corresponde a un nombre de dispositivo de visualización específico:  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo `ClearTypeLevel` de visualización para un usuario, se define un valor DWORD. La siguiente captura de pantalla muestra la configuración del Editor del Registro para el nivel ClearType.  
  
 ![Configuración de ClearType en el Editor del Registro.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]aplicaciones representan texto en uno de los dos modos, con y sin ClearType. Cuando el texto se representa sin ClearType, se conoce como representación en escala de grises.  
  
<a name="gamma_level"></a>
## <a name="gamma-level"></a>Nivel de gamma  
 El nivel de gamma hace referencia a la relación no lineal entre un valor de píxel y la luminancia. El valor de nivel de gamma debe corresponder a las características físicas de la pantalla; de lo contrario, pueden producirse distorsiones en la salida representada. Por ejemplo, el texto puede aparecer demasiado ancho o demasiado estrecho, o los flecos de color pueden aparecer en los bordes de los tallos verticales de los glifos.  
  
 El nivel de gamma es un valor entero comprendido entre 1000 y 2200. El nivel predeterminado es 1900.  
  
### <a name="registry-setting"></a>Configuración del registro  
 La ubicación de la configuración del Registro para el nivel de gamma es una configuración de equipo local que corresponde a un nombre de pantalla específico:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo `GammaLevel` de visualización para un usuario, se define un valor DWORD. La captura de pantalla siguiente muestra la configuración del Editor del Registro para el nivel de gamma.  
  
 ![Configuración de nivel gamma ClearType en el Editor del Registro](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>
## <a name="pixel-structure"></a>Estructura de píxeles  
 La estructura de píxeles describe el tipo de píxeles que componen una pantalla. La estructura de píxeles se define como uno de estos tres tipos:  
  
|Tipo|Value|Descripción|  
|----------|-----------|-----------------|  
|Plano|0|La pantalla no tiene ninguna estructura de píxeles. Esto significa que los orígenes de la luz de cada color se expanden por igual en el área de píxeles, lo que se conoce como representación en escala de grises. Así es como funciona una pantalla estándar. ClearType nunca se aplica al texto representado.|  
|RGB|1|La pantalla tiene píxeles que se componen de tres franjas en el orden siguiente: rojo, verde y azul. ClearType se aplica al texto representado.|  
|BGR|2|La pantalla tiene píxeles que se componen de tres franjas en el orden siguiente: azul, verde y rojo. ClearType se aplica al texto representado. Observe cómo se invierte el orden del tipo RGB.|  
  
 La estructura de píxeles corresponde a un valor entero comprendido entre 0 y 2. El nivel predeterminado es 0, que representa una estructura de píxeles plana.  
  
> [!NOTE]
> Para obtener información sobre cómo enumerar `EnumDisplayDevices`los nombres de dispositivos de visualización, consulte la función Win32.  
  
### <a name="registry-setting"></a>Configuración del registro  
 La ubicación de la configuración del Registro para la estructura de píxeles es una configuración de equipo local que corresponde a un nombre de pantalla específico:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo `PixelStructure` de visualización para un usuario, se define un valor DWORD. La captura de pantalla siguiente muestra la configuración del Editor del Registro para la estructura de píxeles.  
  
 ![Configuración de nivel gamma ClearType en el Editor del Registro](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>
## <a name="text-contrast-level"></a>Nivel de contraste del texto  
 El nivel de contraste del texto permite ajustar la representación de texto en función de los anchos de las franjas de los glifos. El nivel de contraste del texto es un valor entero comprendido entre 0 y 6: cuanto mayor sea el valor entero, más ancha será la franja. El nivel predeterminado es 1.  
  
### <a name="registry-setting"></a>Configuración del registro  
 La ubicación de la configuración del Registro para el nivel de contraste del texto es una configuración de usuario individual que corresponde a un nombre de pantalla específico:  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 Para cada nombre de dispositivo `TextContrastLevel` de visualización para un usuario, se define un valor DWORD. La captura de pantalla siguiente muestra la configuración del Editor del Registro para el nivel de contraste del texto.  
  
 ![Configuración de ClearType en el Editor del Registro.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre ClearType](cleartype-overview.md)
- [Suavizado de contorno de ClearType](/windows/desktop/gdi/cleartype-antialiasing)
