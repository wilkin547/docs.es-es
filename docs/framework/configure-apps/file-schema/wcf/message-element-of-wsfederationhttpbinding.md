---
title: "Elemento &lt;message&gt; de &lt;wsFederationHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Elemento &lt;message&gt; de &lt;wsFederationHttpBinding&gt;
Obtiene la configuración de seguridad a nivel de mensaje para el elemento [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).  
  
## Sintaxis  
  
```  
  
<wsFederationBinding>  
     <binding >  
         <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                              <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
         </message>  
      </security>  
   </binding>  
</wsFederationBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|algorithmSuite|Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.  Vea la tabla de "atributo algorithmSuite" para ver los valores válidos de este atributo.  El valor predeterminado es `Basic256`.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.  Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad \(WS\-SecurityPolicy\).|  
|issuedKeyType|Especifica el tipo de clave que se va a emitir.  Los valores válidos son los siguientes:<br /><br /> -   SymmetricKey<br />-   PublicKey<br /><br /> De manera predeterminada, es `SymmetricKey`.  Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.|  
|issuedTokenType|Una cadena que contiene un URI que especifica el tipo de token que se va a emitir.  De manera predeterminada, es `null`.|  
|negotiateServiceCredential|Un valor booleano que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.  El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.|  
  
## atributo algorithmSuite  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Basic128|Utilice el cifrado Basic128, Sha1 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic192|Utilice el cifrado Basic192, Sha1 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic256|Utilice el cifrado Basic256, Sha1 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic256Rsa15|Utilice Basic256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic192Rsa15|Utilice Basic192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDes|Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic128Rsa15|Utilice Basic128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDesRsa15|Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic128Sha256|Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic192Sha256|Utilice Basic192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic256Sha256|Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|TripleDesSha256|Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic128Sha256Rsa15|Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic192Sha256Rsa15|Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic256Sha256Rsa15|Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDesSha256Rsa15|Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<claimTypeRequirements\>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|Especifica una colección de tipos de demanda para este enlace.  Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.|  
|issuer|Especifica un extremo que emite un token de seguridad.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.|  
|issuerMetadata|Especifica la dirección del extremo del emisor.|  
|[\<tokenRequestParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|Una colección de parámetros de solicitud de token.  Cada parámetro es un elemento XML.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|Define la configuración de seguridad de un enlace.|  
  
## Vea también  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>   
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>   
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>   
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityElement>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)