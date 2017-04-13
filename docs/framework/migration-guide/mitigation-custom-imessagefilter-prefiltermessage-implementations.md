---
title: "Mitigaci&#243;n: personalizar implementaciones de IMessageFilter.PreFilterMessage | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 2
---
# Mitigaci&#243;n: personalizar implementaciones de IMessageFilter.PreFilterMessage
En las aplicaciones de Windows Forms destinadas a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], una implementación <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> personalizada puede filtrar mensajes de forma segura cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> si la implementación <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>:  
  
-   Realiza una o dos de las siguientes acciones:  
  
    -   Agregar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.  
  
    -   Quitar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. .  
  
-   El elemento **And** proporciona mensajes mediante una llamada al método <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.  
  
## Impacto  
 Este cambio solo afecta a aplicaciones de Windows Forms destinadas a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 Para las aplicaciones de Windows Forms destinadas a las versiones anteriores de .NET Framework, como las implementaciones, inician una excepción <xref:System.IndexOutOfRangeException> cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>.  
  
## Mitigación  
 Si no desea que este cambio, las aplicaciones que se destinan a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] pueden excluirse al agregar la siguiente opción de configuración para la sección [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" /> </runtime>  
  
```  
  
 Además, las aplicaciones destinadas a las versiones anteriores de .NET Framework pero se ejecutan en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] pueden incluirse en este comportamiento si se agrega la opción de configuración siguiente para la sección [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" /> </runtime>  
  
```  
  
## Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)