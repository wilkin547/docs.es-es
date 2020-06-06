---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 055b7b49d1f775d49ac20de18c18ca0433716a23
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397862"
---
# \<localIssuer>
Especifica la dirección y el enlace del emisor local que se van a usar para obtener un token de seguridad.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|address|Cadena necesaria. Especifica el URI del emisor local.|  
|binding|Cadena opcional. Uno de los enlaces proporcionados por el sistema. Para obtener una lista, vea [enlaces proporcionados](../../../wcf/system-provided-bindings.md)por el sistema.|  
|bindingConfiguration|Cadena opcional. Especifica una configuración de enlace situada en el archivo de configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Especifica la información de identidad para el emisor local.|  
|[\<headers>](headers-element.md)|Colección de encabezados de dirección necesaria para poder direccionar el emisor local correctamente. Puede utilizar la palabra clave `add` para agregar un encabezado a esta colección.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<issuedToken>](issuedtoken.md)|Especifica un token personalizado usado para autenticar un cliente en un servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Al obtener un token emitido de un Servicio de token de seguridad  (STS), la aplicación cliente se debe configurar con el enlace y la dirección que se van a usar para comunicarse con el STS. Cuando no <xref:System.ServiceModel.WSFederationHttpBinding> proporciona una dirección URL para el servicio de token de seguridad, o cuando la dirección del emisor de un enlace federado es `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null` , el canal de Windows Communication Foundation (WCF) del cliente usa los valores especificados por `address` y `binding` para comunicarse con el STS para obtener el token emitido. Para obtener más información sobre la configuración de un emisor local, consulte [How to: Configure a local issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Procedimiento para configurar un emisor local](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Protección de clientes](../../../wcf/securing-clients.md)
- [Procedimiento para crear un cliente federado](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md)
