---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9118d1462d4790bb457fc8dc2f7c74b6e69de43a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltlocalissuergt"></a>&lt;localIssuer&gt;
Especifica la dirección y el enlace del emisor local que se van a usar para obtener un token de seguridad.  
  
 \<system.ServiceModel>  
\<comportamientos >  
sección endpointBehaviors  
\<comportamiento >  
\<clientCredentials >  
\<issuedToken >  
\<localIssuer >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|address|Cadena necesaria. Especifica el URI del emisor local.|  
|enlace|Cadena opcional. Uno de los enlaces proporcionados por el sistema. Para obtener una lista, vea [enlaces proporcionados](../../../../../docs/framework/wcf/system-provided-bindings.md).|  
|bindingConfiguration|Cadena opcional. Especifica una configuración de enlace situada en el archivo de configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identidad >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Especifica la información de identidad para el emisor local.|  
|[\<encabezados >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Colección de encabezados de dirección necesaria para poder direccionar el emisor local correctamente. Puede utilizar la palabra clave `add` para agregar un encabezado a esta colección.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<issuedToken >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Especifica un token personalizado usado para autenticar un cliente en un servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Al obtener un token emitido de un Servicio de token de seguridad (STS), la aplicación cliente se debe configurar con el enlace y la dirección que se van a usar para comunicarse con el STS. Cuando el <xref:System.ServiceModel.WSFederationHttpBinding> no le haya proporcionado una dirección URL para el servicio de token de seguridad, o cuando la dirección del emisor de un enlace federado es http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous o `null`, el canal del cliente Windows Communication Foundation (WCF) utiliza los valores especificados por `address`y `binding` para comunicarse con STS y obtener el token emitido. Para obtener más información acerca de cómo configurar un emisor local, vea [Cómo: configurar un emisor Local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente establece `address`, `binding`y atributos `bindingConfiguration` de un elemento `localIssuer`.  
  
```xml  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Configuración de un emisor local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)  
 [Creación de un cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
