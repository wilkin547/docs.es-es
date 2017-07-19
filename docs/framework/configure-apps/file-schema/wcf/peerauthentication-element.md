---
title: "&lt;peerAuthentication&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;peerAuthentication&gt; (elemento)
Especifica las opciones de autenticación de clientes punto a punto.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] la programación de igual a igual, vea [Conexión de redes punto a punto](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## Sintaxis  
  
```  
  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`customCertificateValidatorType`|Cadena opcional.  Tipo y ensamblado utilizados para validar un tipo personalizado.  Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.|  
|`certifcateValidationMode`|Enumeración opcional.  Especifica uno de los tres modos utilizados para validar las credenciales.  Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.  De manera predeterminada, es `ChainTrust`.|  
|`revocationMode`|Enumeración opcional.  Uno de los modos utilizados para comprobar listas de certificados revocadas \(CRL\).  De manera predeterminada, es `Online`.|  
|`trustedStoreLocation`|Enumeración opcional.  Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.  Se utiliza este valor cuando un certificado del servicio se negocia al cliente.  La validación se realiza contra el **Personas de confianza** almacén en la ubicación del almacén especificada.  De manera predeterminada, es `CurrentUser`.|  
  
## Atributo customCertificateValidatorType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|String|Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.  Como mínimo, se requieren un espacio de nombres y un nombre de tipo.  La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.|  
  
## Atributo certificateValidationMode  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.  De manera predeterminada, es `ChainTrust`.<br /><br /> Para obtener más información, consulta [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Atributo revocationMode  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.  De manera predeterminada, es `Online`.<br /><br /> Para obtener más información, consulta [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Atributo trustedStoreLocation  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.  De manera predeterminada, es `CurrentUser`.  Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.  Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.|  
  
## Comentarios  
 El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.  Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla.  Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde.  El validador del contestador se invoca para comprobar la credencial de la parte remota.  Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.  
  
## Ejemplo  
 El código siguiente establece el modo de validación de certificados en `PeerOrChainTrust`.  
  
```  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
     <peerAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
     <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>   
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>   
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>   
 [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Conexión de redes punto a punto](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/es-es/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/es-es/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Protección de las aplicaciones de canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)