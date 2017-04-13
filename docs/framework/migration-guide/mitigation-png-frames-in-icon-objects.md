---
title: "Mitigaci&#243;n: marcos PNG en objetos de icono | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Mitigaci&#243;n: marcos PNG en objetos de icono
A partir de .NET Framework 4.6, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> convierte correctamente iconos con marcos PNG en objetos <xref:System.Drawing.Bitmap>.  
  
 En aplicaciones destinadas a .NET Framework 4.5.2 y versiones anteriores, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> genera una excepción <xref:System.ArgumentOutOfRangeException> si el objeto <xref:System.Drawing.Icon> tiene marcos PNG.  
  
## Impacto  
 Este cambio afecta a las aplicaciones que se vuelven a compilar para tener como destino .NET Framework 4.6 y que implementan un control especial para <xref:System.ArgumentOutOfRangeException> que se genera cuando un objeto <xref:System.Drawing.Icon> tiene marcos PNG. Cuando se ejecuta en .NET Framework 4.6, la conversión es correcta, ya no se genera un <xref:System.ArgumentOutOfRangeException> y, por tanto, ya no se invoca el controlador de excepciones.  
  
### Mitigación  
 Si no desea este comportamiento, puede conservar el comportamiento anterior agregando el siguiente elemento en la sección [\< runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:  
  
```  
<AppContextSwitchOverrides value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
  
```  
  
 Si el archivo app.config ya contiene el elemento `AppContextSwitchOverrides`, el nuevo valor se debe combinar con el atributo `value` como este:  
  
```  
<AppContextSwitchOverrides value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
  
```  
  
## Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)