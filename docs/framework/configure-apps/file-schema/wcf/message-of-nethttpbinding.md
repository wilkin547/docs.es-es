---
title: '&lt;message&gt; de &lt;netHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 30098d2b9a9087eb0543bdd7c8a899cd66c91ed8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515187"
---
# <a name="ltmessagegt-of-ltnethttpbindinggt"></a>&lt;message&gt; de &lt;netHttpBinding&gt;
Define la configuración de seguridad de nivel de mensaje de la [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 \<system.ServiceModel>  
\<enlaces >  
\<netHttpBinding>  
\<enlace >  
\<seguridad >  
\<mensaje >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|algorithmSuite|Establece el cifrado de mensajes y los algoritmos de encapsulado de claves. Este atributo es de tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, que especifica los algoritmos y los tamaños clave. Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).<br /><br /> El valor predeterminado es `Basic256`.|  
|clientCredentialType|Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad basada en mensaje. De manera predeterminada, es `UserName`.|  
  
## <a name="clientcredentialtype-attribute"></a>Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|UserName|-Requiere la autenticación del cliente al servidor con una credencial UserName. Esta credencial se tiene que especificar mediante el elemento <`clientCredentials`>.<br />-WCF no admite enviar un resumen de contraseña ni derivar claves mediante contraseñas y utilizando tales claves para seguridad de mensajes. Por lo tanto, WCF impone que el transporte sea seguro al usar credenciales UserName. Para `basicHttpBinding`, esto requiere configurar un canal de SSL.|  
|Certificado|Exige la autenticación del cliente en el servidor mediante un certificado. En este caso la credencial de cliente se tiene que especificar con <`clientCredentials`> y <`clientCertificate`> Además, cuando se utiliza el modo de seguridad de mensajes, se debe proporcionar el cliente con el certificado del servicio. La credencial del servicio en este caso necesita ser especificada utilizando <xref:System.ServiceModel.Description.ClientCredentials> clase o `ClientCredentials` elemento de comportamiento especificando el servicio de certificado mediante el \<serviceCertificate > elemento de serviceCredentials.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|<`security`> elemento de <`netHttpBinding`>|Define las funciones de seguridad del elemento <`netHttpBinding`>.|  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra cómo implementar una aplicación que utiliza basicHttpBinding y modo de seguridad. En el ejemplo de configuración de un servicio siguiente, la definición de extremo especifica basicHttpBinding y hace referencia a una configuración de enlace denominada `Binding1`. El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección `behaviors` del archivo de configuración bajo el elemento `serviceCredentials`. El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección `behaviors` bajo el elemento `clientCertificate`.  
  
 El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.  
  
```xml  
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
  
## <a name="see-also"></a>Vea también  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<enlace >](../../../../../docs/framework/misc/binding.md)
