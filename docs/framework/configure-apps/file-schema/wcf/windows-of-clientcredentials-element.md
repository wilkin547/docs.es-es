---
title: Elemento &lt;windows&gt; de &lt;clientCredentials&gt;
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 9badcfafff4bc09a16b0b9a565a9ea5c01e26bb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a>Elemento &lt;windows&gt; de &lt;clientCredentials&gt;
Especifica los valores para una credencial de Windows que se va a utilizar para representar al cliente.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors >  
\<comportamiento >  
\<clientCredentials >  
\<Windows >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|Establece la preferencia de suplantación que el cliente comunica al servidor. El modo de suplantación que el cliente elige no se exige en el servidor. Los valores válidos son los siguientes:<br /><br /> -Identificación: El servidor puede obtener la identidad y privilegios del cliente, pero no puede suplantar al cliente.<br />-Suplantación: El servidor puede suplantar el contexto de seguridad del cliente en el sistema local.<br />-Delegation: El servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.<br />-Anónima: El servidor no se puede suplantar o identificar al cliente.<br />-Ninguno: Un nivel de suplantación no está asignado.<br /><br /> El valor predeterminado es Identification. Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.|  
|`allowNtlm`|Establecer esta propiedad en `true` permite a la autenticación degradar a NTLM si Kerberos no está disponible.<br /><br /> Si se establece esta propiedad en `false` hace que Windows Communication Foundation (WCF) para realizar un mayor esfuerzo por producir una excepción si se utiliza NTLM. Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica las credenciales utilizadas para autenticar el cliente al servicio.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)  
 [Trabajo con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
