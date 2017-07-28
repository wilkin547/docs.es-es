---
title: "Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ef3e03edef48676e2e32201b422c66f117487907
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage
En las aplicaciones de Windows Forms destinadas a versiones de .NET Framework a partir de [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], una implementación de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> personalizada puede filtrar mensajes de forma segura cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> si la implementación de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>:  
  
-   Realiza una o dos de las siguientes acciones:  
  
    -   Agregar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.  
  
    -   Quitar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. .  
  
-   El elemento **And** proporciona mensajes mediante una llamada al método <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.  
  
## <a name="impact"></a>Impacto  
 Este cambio solo afecta a aplicaciones de Windows Forms que tienen como destino versiones de .NET Framework a partir de [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 Para las aplicaciones de Windows Forms destinadas a las versiones anteriores de .NET Framework, en algunos casos, tales implementaciones inician una excepción <xref:System.IndexOutOfRangeException> cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>.  
  
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

