---
title: "Mitigación: constructor ClaimsIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 946903f1-0fbf-4f67-805b-1eb48352024d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a50cbd69aa1f2c72adc9fc4d10a070f5faa0cf54
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-claimsidentity-constructor"></a>Mitigación: constructor ClaimsIdentity
A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], hay un cambio en cómo el constructor <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> establece la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>. Si el argumento <xref:System.Security.Principal.IIdentity> es un objeto <xref:System.Security.Claims.ClaimsIdentity> y la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> de ese objeto <xref:System.Security.Claims.ClaimsIdentity> no es `null`, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> se conecta mediante el método <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName>. En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> se asocia como una referencia existente.  
  
## <a name="impact"></a>Impacto  
 A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> del nuevo objeto <xref:System.Security.Claims.ClaimsIdentity> no es igual a la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> del argumento <xref:System.Security.Principal.IIdentity> del constructor. En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y en versiones anteriores, sí es igual.  
  
## <a name="mitigation"></a>Mitigación  
 Si no desea este comportamiento, puede restaurar el comportamiento anterior si establece el modificador `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` en el archivo de configuración de la aplicación en `true`. Para ello, es necesario que agregue lo siguiente a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo web.config:  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

