---
title: "Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d85c827b414cc94410a921bfae9ce3e1764d22ea
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage
En las aplicaciones de Windows Forms que tienen como destino versiones .NET Framework a partir de [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], una implementación personalizada <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> puede filtrar de forma segura los mensajes cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> si la implementación <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>:  
  
-   Realiza una o dos de las siguientes acciones:  
  
    -   Agrega un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.  
  
    -   Agrega un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. .  
  
-   **Y** proporciona mensajes mediante una llamada al método <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.  
  
## <a name="impact"></a>Impacto  
 Este cambio solo afecta a aplicaciones de Windows Forms que tienen como destino versiones de .NET Framework a partir de [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 En el caso de las aplicaciones de Windows Forms que tienen como destino versiones anteriores de .NET Framework, en algunos casos dichas implementaciones generan una excepción <xref:System.IndexOutOfRangeException> cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>.  
  
## <a name="mitigation"></a>Mitigación  
 Si no desea este cambio, las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o una versión posterior pueden excluirse si agregan el siguiente ajuste de configuración a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
```  
  
 Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o una versión posterior pueden incluirse en este comportamiento si agregan el siguiente ajuste de configuración a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)

