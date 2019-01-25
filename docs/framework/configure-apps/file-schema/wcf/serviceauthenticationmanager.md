---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: fd04b10c0ac0bef4087daa1012a1b8bd3a5880e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493643"
---
# <a name="ltserviceauthenticationmanagergt"></a>&lt;serviceAuthenticationManager&gt;
Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, un mensaje o un autor en el nivel del servicio.  
  
\<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
\<serviceAuthenticationManager>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|serviceAuthenticationManagerType|Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
