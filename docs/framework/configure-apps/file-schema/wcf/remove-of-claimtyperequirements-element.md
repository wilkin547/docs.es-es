---
title: '&lt;remove&gt; del elemento &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 5d1f9c963792336f0938113beefbdef770831e9d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753253"
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a>&lt;remove&gt; del elemento &lt;claimTypeRequirements&gt;
Especifica los tipos de notificaciones que se van a quitar en la credencial aliada.  
  
 \<system.ServiceModel>  
\<enlaces >  
\<wsFederatedBinding >  
\<enlace >  
\<seguridad >  
\<mensaje >  
\<claimTypeRequirements >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<claimTypeRequirements>  
      <remove claimType="URI" />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|claimType|URI que define el tipo de una notificación que se va a eliminar.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<claimTypeRequirements >](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|Especifica una colección de tipos de notificación requeridos. Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.<br /><br /> En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada. Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación. Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
