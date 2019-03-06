---
title: <transport> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 4d84d99660e4804a5eff2e343ba01c2983520b8f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379736"
---
# <a name="transport-of-nethttpbinding"></a>\<transporte > de \<netHttpBinding >
Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.  
  
\<system.serviceModel>  
\<bindings>  
\<netHttpBinding>  
\<binding>  
\<security>  
\<transport>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|clientCredentialType|: Especifica el tipo de credencial que se usará al realizar la autenticación de cliente mediante la autenticación HTTP.  De manera predeterminada, es `None`. Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|: Especifica el tipo de credencial que se usará al realizar la autenticación de cliente desde dentro de un dominio mediante un proxy a través de HTTP. Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`. Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|realm|Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita. El valor predeterminado es una cadena vacía.|  
|policyEnforcement|Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).<br />2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.<br />3.  Always: la directiva siempre se aplica. Los clientes que no admitan la protección extendida no podrán autenticarse.|  
|protectionScenario|Esta enumeración especifica el escenario de protección que exige la directiva.|  
  
## <a name="clientcredentialtype-attribute"></a>Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|Los mensajes no se protegen durante la transferencia.|  
|Básico|Especifica la autenticación básica.|  
|Implícita|Especifica la autenticación implícita.|  
|Ntlm|Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.|  
|Windows|Especifica la autenticación de Windows integrada.|  
  
## <a name="proxycredentialtype-attribute"></a>Atributo proxyCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|-Los mensajes no están protegidos durante la transferencia.|  
|Básico|Especifica la autenticación básica como se define en RFC 2617 – HTTP Authentication: Básica y autenticación implícita.|  
|Implícita|Especifica la autenticación implícita, como se define en RFC 2617 – HTTP Authentication: Básica y autenticación implícita.|  
|Ntlm|Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.|  
|Windows|Especifica la autenticación de Windows integrada.|  
|Certificado|Realiza la autenticación del cliente mediante un certificado. Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|Define las funciones de seguridad para el [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).|  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico. De forma predeterminada, el enlace básico soporta la comunicación HTTP.  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../../../docs/framework/wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
