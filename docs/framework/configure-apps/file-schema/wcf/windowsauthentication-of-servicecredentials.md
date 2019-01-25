---
title: Elemento &lt;windowsAuthentication&gt; de &lt;serviceCredentials&gt;
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: 3077baf49c13c91c6293823aa841525bf07ca7f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616269"
---
# <a name="ltwindowsauthenticationgt-of-ltservicecredentialsgt"></a>Elemento &lt;windowsAuthentication&gt; de &lt;serviceCredentials&gt;
Especifica los valores de una credencial del servicio de Windows.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
\<serviceCredentials>  
\<windowsAuthentication>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`includeWindowsGroups`|Un atributo booleano opcional que especifica si el sistema incluye los grupos de Windows en el contexto de seguridad. De manera predeterminada, es `true`.<br /><br /> Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa. Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.|  
|`allowAnonymousLogons`|Un atributo booleano opcional que especifica si se permiten las llamadas anónimas, no autenticadas. De manera predeterminada, es `false`.<br /><br /> Cuando el atributo `clientCredentialType` de un enlace está establecido en `Windows`, el sistema no permite las llamadas anónimas. Esto significa que sólo los llamadores autenticados del dominio o grupo de trabajo tienen acceso al sistema. Se puede reemplazar este comportamiento utilizando este atributo.<br /><br /> Utilice esta configuración con extrema precaución.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## <a name="remarks"></a>Comentarios  
 Utilice este elemento para especificar si se permite a los usuarios anónimos de Windows obtener acceso estableciendo el atributo `allowAnonymousLogons`. También puede especificar si se incluye información del grupo a la que pertenecen los usuarios en AuthorizationContext estableciendo el atributo `includeWindowsGroups`. Si se establece como `true` (valor predeterminado), el servicio puede determinar los grupos de Windows a los que pertenece el cliente.  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
