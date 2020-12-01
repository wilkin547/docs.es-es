---
title: 'Mitigación: marcos PNG en objetos de icono'
description: Aprenda a configurar el comportamiento de los marcos PNG en objetos de icono si el nuevo comportamiento incluido en .NET Framework 4.6 y versiones posteriores no es el deseado.
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
ms.openlocfilehash: a8bb4fca19a09f16c89ce8c5da08ebcae9a037ec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276586"
---
# <a name="mitigation-png-frames-in-icon-objects"></a>Mitigación: marcos PNG en objetos de icono

A partir de .NET Framework 4.6, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> convierte correctamente iconos con marcos PNG en objetos <xref:System.Drawing.Bitmap> .  
  
 En aplicaciones destinadas a .NET Framework 4.5.2 y versiones anteriores, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> genera una excepción <xref:System.ArgumentOutOfRangeException> si el objeto <xref:System.Drawing.Icon> tiene marcos PNG.  
  
## <a name="impact"></a>Impacto  

 Este cambio afecta a las aplicaciones que se vuelven a compilar para tener como destino .NET Framework 4.6 y que implementan un control especial para <xref:System.ArgumentOutOfRangeException> que se genera cuando un objeto <xref:System.Drawing.Icon> tiene marcos PNG. Cuando se ejecuta en .NET Framework 4.6, la conversión es correcta, ya no se genera un <xref:System.ArgumentOutOfRangeException> y, por tanto, ya no se invoca el controlador de excepciones.  
  
### <a name="mitigation"></a>Mitigación  

 Si no quiere este comportamiento, puede conservar el comportamiento anterior agregando el elemento siguiente a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 Si el archivo app.config ya contiene el elemento `AppContextSwitchOverrides` , el nuevo valor se debe combinar con el atributo `value` como este:  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;previous key=previous-value" />
```
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
