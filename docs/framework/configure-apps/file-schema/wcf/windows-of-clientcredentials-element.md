---
title: <windows> del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 115e1822659c04ee37a7364f7b25616b52dc5efe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177831"
---
# <a name="windows-of-clientcredentials-element"></a>\<windows> del \<clientCredentials> elemento

Especifica los valores para una credencial de Windows que se va a utilizar para representar al cliente.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|Establece la preferencia de suplantación que el cliente comunica al servidor. El modo de suplantación que el cliente elige no se exige en el servidor. Los valores válidos incluyen los siguientes:<br /><br /> -Identification: el servidor puede obtener la identidad y los privilegios del cliente, pero no puede suplantar al cliente.<br />-Impersonation: el servidor puede suplantar el contexto de seguridad del cliente en el sistema local.<br />-Delegation: el servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.<br />-Anonymous: el servidor no puede suplantar o identificar al cliente.<br />-None: no se ha asignado un nivel de suplantación.<br /><br /> El valor predeterminado es Identification. Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.|  
|`allowNtlm`|Establecer esta propiedad en `true` permite a la autenticación degradar a NTLM si Kerberos no está disponible.<br /><br /> Establecer esta propiedad en `false` hace que Windows Communication Foundation (WCF) realice un mejor esfuerzo para producir una excepción si se utiliza NTLM. Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Especifica las credenciales utilizadas para autenticar el cliente al servicio.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [Protección de clientes](../../../wcf/securing-clients.md)
- [Trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
