---
title: "&lt;message&gt; de &lt;netHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;message&gt; de &lt;netHttpBinding&gt;
Define la configuración de seguridad de nivel de mensaje para un enlace [\<basicHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
## Sintaxis  
  
```  
  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|algorithmSuite|Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.  Este atributo es de tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, que especifica los algoritmos y los tamaños clave.  Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad \(WS\-SecurityPolicy\).<br /><br /> El valor predeterminado es `Basic256`.|  
|clientCredentialType|Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad basada en mensaje.  De manera predeterminada, es `UserName`.|  
  
## Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|UserName|-   Requiere que el cliente se autentique al servidor con una credencial UserName.  Esta credencial se tiene que especificar mediante el elemento \<`clientCredentials`\>.<br />-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] no permite enviar un resumen de contraseña ni derivar claves mediante contraseñas, así como tampoco usar dichas claves para seguridad de mensajes.  Por lo tanto, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] garantiza que el transporte sea seguro al usar credenciales UserName.  Para `basicHttpBinding`, esto requiere configurar un canal de SSL.|  
|Certificado|Exige la autenticación del cliente en el servidor mediante un certificado.  En este caso la credencial de cliente se tiene que especificar con \<`clientCredentials`\> y \<`clientCertificate`\>  Además, cuando se utiliza el modo de seguridad de mensajes, se debe proporcionar el cliente con el certificado del servicio.  Las credenciales del servicio en este caso tienen que especificarse con la clase <xref:System.ServiceModel.Description.ClientCredentials> o el elemento de comportamiento `ClientCredentials`, especificando el certificado de servicio mediante el elemento \<serviceCertificate\> de serviceCredentials.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|\<elemento `security`\> de \<`netHttpBinding`\>|Define las funciones de seguridad del elemento \<`netHttpBinding`\>.|  
  
## Ejemplo  
 Este ejemplo muestra cómo implementar una aplicación que utiliza basicHttpBinding y modo de seguridad.  En el ejemplo de configuración de un servicio siguiente, la definición de extremo especifica basicHttpBinding y hace referencia a una configuración de enlace denominada `Binding1`.  El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección `behaviors` del archivo de configuración bajo el elemento `serviceCredentials`.  El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección `behaviors` bajo el elemento `clientCertificate`.  
  
 El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.  
  
```  
<system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
      <basicHttpBinding>  
        <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1" >  
          <security mode = "Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--  
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
</system.serviceModel>  
```  
  
## Vea también  
 <xref:System.ServiceModel.NetHttpMessageSecurity>   
 <xref:System.ServiceModel.Configuration.NetHttpSecurityElement.Message%2A>   
 <xref:System.ServiceModel.NetHttpSecurity.Message%2A>   
 <xref:System.ServiceModel.Configuration.NetHttpMessageSecurityElement>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)