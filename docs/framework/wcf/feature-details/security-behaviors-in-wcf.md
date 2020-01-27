---
title: Comportamientos de seguridad en WCF
ms.date: 03/30/2017
ms.assetid: 513232c0-39fd-4409-bda6-5ebd5e0ea7b0
ms.openlocfilehash: 12ae9bb90752fe3ee76404948693c501fc42efe6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76730941"
---
# <a name="security-behaviors-in-wcf"></a>Comportamientos de seguridad en WCF
En Windows Communication Foundation (WCF), los comportamientos modifican el comportamiento de tiempo de ejecución en el nivel de servicio o en el nivel de extremo. (Para obtener más información sobre los comportamientos en general, vea [especificar el comportamiento de tiempo de ejecución del servicio](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)). Los *comportamientos de seguridad* permiten el control sobre credenciales, autenticación, autorización y registros de auditoría. Puede utilizar comportamientos mediante programación o a través de configuración. Este tema se centra en la configuración de los siguientes comportamientos relacionados con las funciones de seguridad:  
  
- [\<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
- [\<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).  
  
- [\<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md).  
  
- [\<serviceSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md).  
  
- [\<serviceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md), que también le permite especificar un extremo seguro al que los clientes pueden tener acceso para los metadatos.  
  
## <a name="setting-credentials-with-behaviors"></a>Establecimiento de credenciales con comportamientos  
 Use las [\<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) y [\<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) para establecer los valores de credenciales de un servicio o cliente. La configuración de enlace subyacente determina si una credencial tiene que establecerse. Por ejemplo, si el modo de seguridad está establecido en `None`, clientes y servicios no se autentican entre sí y no requieren credenciales de ningún tipo.  
  
 Por otro lado, el enlace de servicio puede requerir un tipo de credencial de cliente. En ese caso, puede tener que establecer un valor de credencial mediante un comportamiento. (Para obtener más información acerca de los posibles tipos de credenciales, consulte [seleccionar un tipo de credencial](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)). En algunos casos, como cuando se usan las credenciales de Windows para la autenticación, el entorno establece automáticamente el valor de la credencial real y no es necesario establecer explícitamente el valor de la credencial (a menos que desee especificar un conjunto de credenciales diferente).  
  
 Todas las credenciales del servicio se encuentran como elementos secundarios del [\<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md). El siguiente ejemplo muestra un certificado utilizado como una credencial de servicio.  
  
```xml  
<configuration>  
 <system.serviceModel>  
  <behaviors>  
   <serviceBehaviors>  
    <behavior name="ServiceBehavior1">  
     <serviceCredentials>  
      <serviceCertificate findValue="000000000000000000000000000"   
                          storeLocation="CurrentUser"  
      storeName="Root" x509FindType="FindByThumbprint" />  
     </serviceCredentials>  
    </behavior>  
   </serviceBehaviors>  
  </behaviors>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="service-credentials"></a>Credenciales de servicio  
 El [> de\<serviceCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) contiene cuatro elementos secundarios. Los elementos y sus usos se discuten en las siguientes secciones.  
  
### <a name="servicecertificate-element"></a>\<elemento > serviceCertificate  
 Use este elemento para especificar un certificado X.509 que se usará para autenticar el servicio a los clientes utilizando el modo de seguridad de mensajes. Si está usando un certificado que se renueva periódicamente, su huella digital cambiará. En ese caso, utilice el nombre del asunto como el `X509FindType` porque el certificado se puede volver a emitir con el mismo nombre de asunto.  
  
 Para obtener más información sobre el uso del elemento, vea [Cómo: especificar valores de credenciales de cliente](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
### <a name="certificate-of-clientcertificate-element"></a>\<> de certificados del elemento \<clientCertificate >  
 Use el elemento [\<> de certificados](../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md) cuando el servicio deba tener el certificado del cliente de antemano para comunicarse de forma segura con el cliente. Esto se produce al utilizar el patrón de comunicación dúplex. En el patrón de solicitud-respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para proteger su respuesta de vuelta hasta el cliente. El patrón de comunicación dúplex, sin embargo, no tiene ninguna solicitud ni respuesta. El servicio no puede inferir el certificado del cliente a partir de la comunicación y, por consiguiente, el servicio necesita tener de antemano el certificado del cliente para proteger los mensajes destinados al cliente. Debe obtener el certificado del cliente de una manera fuera de banda y especificar el certificado usando este elemento. Para obtener más información sobre los servicios dúplex, consulte [Cómo: crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
### <a name="authentication-of-clientcertificate-element"></a>\<> de autenticación de \<elemento > clientCertificate  
 El elemento [\<authentication >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) le permite personalizar cómo se autentican los clientes. Puede establecer el atributo `CertificateValidationMode` en `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` o `Custom`. De forma predeterminada, el nivel se establece en `ChainTrust`, que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una *entidad de certificación raíz* en la parte superior de la cadena. Este es el modo más seguro. También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza. Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza. Al implementar un cliente, utilice en su lugar el valor `ChainTrust`. También puede establecer el valor en `Custom`. Cuando se establezca en el valor `Custom`, también debe establecer el atributo `CustomCertificateValidatorType` en un ensamblado y tipo utilizados para validar el certificado. Para crear su propio validador personalizado, debe heredar a partir de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator> abstracta.  
  
### <a name="issuedtokenauthentication-element"></a>\<elemento > issuedTokenAuthentication  
 El escenario del token emitido tiene tres etapas. En la primera fase, un cliente que intenta obtener acceso a un servicio se conoce como *servicio de token seguro* (STS). El STS autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML). El cliente vuelve a continuación al servicio con el token. El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente. Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro. El elemento [\<issuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) es el repositorio para cualquier certificado de servicio de token seguro. Para agregar certificados, use el [\<knownCertificates >](../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). Inserte un [\<agregar >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad. Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.  
  
 Debe usar la colección [\<allowedAudienceUris >](../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md) en una aplicación federada que utilice un servicio de *token seguro* (STS) que emita `SamlSecurityToken` tokens de seguridad. Cuando el STS emite el token de seguridad, puede especificar el URI de los servicios Web para el que está dirigido el token de seguridad mediante la agregación de una `SamlAudienceRestrictionCondition` al token de seguridad. Eso le permite al `SamlSecurityTokenAuthenticator` del servicio Web del destinatario comprobar que el token de seguridad emitido está dirigido a este servicio Web especificando que esta comprobación debería tener lugar haciendo lo siguiente:  
  
- Establezca el `audienceUriMode` atributo de [\<issuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) en `Always` o `BearerKeyOnly`.  
  
- Especifique el conjunto de identificadores URI válidos, agregando los URI a esta colección. Para ello, inserte un [\<agregar >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md) para cada URI  
  
 Para obtener más información, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 Para obtener más información sobre el uso de este elemento de configuración, consulte [Cómo: configurar credenciales en un servicio de Federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
#### <a name="allowing-anonymous-cardspace-users"></a>Permitir usuario anónimos CardSpace  
 Mediante el establecimiento del atributo `AllowUntrustedRsaIssuers` del elemento `<IssuedTokenAuthentication>` en `true` de manera explícita, se permite a cualquier cliente presentar un token autoemitido firmado con un par de claves de RSA arbitrario. El emisor no es de *confianza* porque la clave no tiene datos de emisor asociados. Un usuario de CardSpace puede crear una tarjeta autoemitida que incluye las notificaciones de identidad proporcionadas por sí misma. Utilice esta función con precaución. Para usar esta característica, piense en la clave pública de RSA como una contraseña más segura que debería almacenarse en una base de datos junto con un nombre de usuario. Antes de permitir que un cliente obtenga acceso al servicio, compruebe la clave pública de RSA presentada por el cliente comparándola con la clave pública almacenada para el nombre de usuario presentado. Esto supone que ha establecido con que un proceso de registro por el que los usuarios pueden registrar sus nombres de usuario y asociarlos con las claves públicas de RSA autoemitidas.  
  
## <a name="client-credentials"></a>Credenciales de cliente  
 Las credenciales de cliente se utilizan para autenticar al cliente en los servicios en casos donde se requiere autenticación mutua. Puede utilizar la sección para especificar los certificados de servicio para escenarios donde el cliente debe proteger los mensajes para un servicio con el certificado del servicio.  
  
 También puede configurar un cliente como parte de un escenario de federación para usar tokens emitidos a partir de un servicio de tokens seguros o un emisor local de tokens. Para obtener más información sobre los escenarios federados, vea [Federación y tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md). Todas las credenciales del cliente se encuentran en el [\<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md), tal y como se muestra en el código siguiente.  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="EndpointBehavior1">  
   <clientCredentials>  
    <clientCertificate findValue="cn=www.contoso.com"     
        storeLocation="LocalMachine"  
        storeName="AuthRoot" x509FindType="FindBySubjectName" />  
    <serviceCertificate>  
     <defaultCertificate findValue="www.cohowinery.com"   
                    storeLocation="LocalMachine"  
                    storeName="Root" x509FindType="FindByIssuerName" />  
    <authentication revocationMode="Online"  
                    trustedStoreLocation="LocalMachine" />  
    </serviceCertificate>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
```  
  
#### <a name="clientcertificate-element"></a>\<elemento > clientCertificate  
 Establezca el certificado utilizado para autenticar al cliente con este elemento. Para obtener más información, vea [Cómo: especificar valores de credencial de cliente](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
#### <a name="httpdigest"></a>\<httpDigest>  
 Esta característica se debe habilitar con Active Directory en Windows e Internet Information Services (IIS). Para obtener más información, vea [autenticación implícita en IIS 6,0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).  
  
#### <a name="issuedtoken-element"></a>\<elemento > issuedToken  
 El [\<issuedToken >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) contiene los elementos utilizados para configurar un emisor local de tokens, o los comportamientos utilizados con un servicio de token de seguridad. Para obtener instrucciones sobre cómo configurar un cliente para utilizar un emisor local, consulte [How to: Configure a local issuer](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
#### <a name="localissueraddress"></a>\<localIssuerAddress>  
 Especifica una dirección de servicio de token de seguridad predeterminada. Se utiliza cuando el <xref:System.ServiceModel.WSFederationHttpBinding> no proporciona una dirección URL para el servicio de token de seguridad, o cuando la dirección del emisor de un enlace federado es `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null`. En casos como éste, las <xref:System.ServiceModel.Description.ClientCredentials> deben configurarse con la dirección del emisor local y el enlace que se va a utilizar para comunicarse con ese emisor.  
  
#### <a name="issuerchannelbehaviors"></a>\<issuerChannelBehaviors>  
 Use el [\<issuerChannelBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md) para agregar comportamientos de cliente WCF utilizados al comunicarse con un servicio de token de seguridad. Defina los comportamientos de cliente en la sección [\<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) . Para usar un comportamiento definido, agregue un <`add`> elemento al elemento `<issuerChannelBehaviors>` con dos atributos. Establezca la `issuerAddress` en la dirección URL del servicio de token de seguridad y establezca el atributo `behaviorConfiguration` en el nombre del comportamiento del punto de conexión definido, tal y como se muestra en el ejemplo siguiente.  
  
```xml  
<clientCredentials>  
   <issuedToken>  
      <issuerChannelBehaviors>  
         <add issuerAddress="http://www.contoso.com"  
               behaviorConfiguration="clientBehavior1" />     
```  
  
#### <a name="servicecertificate-element"></a>\<elemento > serviceCertificate  
 Utilice este elemento para controlar autenticación de certificados de servicio.  
  
 El elemento [\<defaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) puede almacenar un solo certificado que se utiliza cuando el servicio no especifica ningún certificado.  
  
 Use el [\<scopedCertificates](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md) y [\<agregar >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md) para establecer certificados de servicio asociados a servicios específicos. El elemento `<add>` incluye un atributo `targetUri` que se utilice para asociar el certificado al servicio.  
  
 El elemento [\<authentication >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) especifica el nivel de confianza utilizado para autenticar los certificados. De forma predeterminada, el nivel está establecido en "ChainTrust", que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una entidad emisora de certificados de confianza en la parte superior de la cadena. Este es el modo más seguro. También puede establecer el valor en “PeerOrChainTrust”, que especifica que los certificados autoemitidos (confianza de mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza. Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza. Al implementar un cliente, utilice en su lugar el valor “ChainTrust”. También puede establecer el valor en “Custom” o “None”. Para usar el valor "Custom", también debe establecer el atributo `CustomCertificateValidatorType` en un ensamblado y tipo utilizados para validar el certificado. Para crear su propio validador personalizado, debe heredar a partir de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator> abstracta. Para obtener más información, consulte [Cómo: crear un servicio que emplee un validador de certificado personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 El elemento de [> de autenticación de\<](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) incluye un atributo `RevocationMode` que especifica cómo se comprueba la revocación de los certificados. El valor predeterminado es "online", que indica que la revocación de los certificados se comprueba automáticamente. Para obtener más información, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="serviceauthorization"></a>ServiceAuthorization  
 El elemento [\<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) contiene elementos que afectan a la autorización, a los proveedores de roles personalizados y a la suplantación.  
  
 La clase <xref:System.Security.Permissions.PrincipalPermissionAttribute> se aplica a un método de servicio. El atributo especifica los grupos de usuarios que se han de utilizar al autorizar el uso de un método protegido. El valor predeterminado es "UseWindowsGroups" y especifica que en los grupos de Windows, como "Administradores" o "Usuarios", se busca una identidad que intente obtener acceso a un recurso. También puede especificar "UseAspNetRoles" para usar un proveedor de roles personalizado que esté configurado en el <`system.web` elemento >, como se muestra en el código siguiente.  
  
```xml  
<system.web>  
  <membership defaultProvider="SqlProvider"   
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add   
          name="SqlProvider"   
          type="System.Web.Security.SqlMembershipProvider"   
          connectionStringName="SqlConn"  
          applicationName="MembershipProvider"  
          enablePasswordRetrieval="false"  
          enablePasswordReset="false"  
          requiresQuestionAndAnswer="false"  
          requiresUniqueEmail="true"  
          passwordFormat="Hashed" />  
     </providers>  
   </membership>  
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 El ejemplo de código siguiente muestra el `roleProviderName` utilizado con el atributo `principalPermissionMode`.  
  
```xml  
<behaviors>  
 <behavior name="ServiceBehaviour">          
  <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                        roleProviderName ="SqlProvider" />  
</behavior>   
   <!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
## <a name="configuring-security-audits"></a>Configuración de auditorías de seguridad  
 Use el [\<serviceSecurityAudit](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) para especificar el registro en el que se escribe y los tipos de eventos que se van a registrar. Para obtener más información, consulte [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
```xml  
<system.serviceModel>  
<serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceSecurityAudit auditLogLocation="Application"   
             suppressAuditFailure="true"  
             serviceAuthorizationAuditLevel="Success"   
             messageAuthenticationAuditLevel="Success" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="secure-metadata-exchange"></a>Intercambio seguro de metadatos  
 Exportar los metadatos a los clientes es conveniente para los desarrolladores de clientes y servicios, puesto que permite la descarga de configuración y código de cliente. Para reducir la exposición de un servicio a los usuarios malintencionados, es posible proteger la transferencia mediante el mecanismo SSL sobre HTTP (HTTPS). Para realizar esto, debe enlazar primero un certificado X.509 adecuado a un puerto concreto en el equipo que esté hospedando el servicio. (Para obtener más información, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)). En segundo lugar, agregue un [\<serviceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) a la configuración del servicio y establezca el atributo `HttpsGetEnabled` en `true`. Finalmente, establezca el atributo `HttpsGetUrl` en la dirección URL del punto de conexión de metadatos del servicio, tal y como se muestra en el ejemplo siguiente.  
  
```xml  
<behaviors>  
 <serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceMetadata httpsGetEnabled="true"   
     httpsGetUrl="https://myComputerName/myEndpoint" />  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>Vea también

- [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
