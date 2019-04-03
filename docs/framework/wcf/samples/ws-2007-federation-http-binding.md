---
title: Enlace HTTP de federación de WS 2007
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: f6d31de62420a8de8e1ac865918b600e7864a5d1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834457"
---
# <a name="ws-2007-federation-http-binding"></a>Enlace HTTP de federación de WS 2007
Este ejemplo muestra el uso de <xref:System.ServiceModel.WS2007FederationHttpBinding>, un enlace estándar que puede utilizar para generar escenarios federados que admiten la versión 1.3 de la especificación WS-Trust.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El ejemplo está compuesto de un programa cliente basado (Client.exe) en consola, un programa de servicio de token de seguridad basado (Securitytokenservice.exe) en consola y un programa de servicio basado (Service.exe) en consola. El servicio implementa un contrato que define un patrón de comunicación de solicitud/respuesta. La interfaz `ICalculator`, que expone las operaciones matemáticas (`Add`, `Subtract`, `Multiply`y `Divide`) define el contrato. El cliente obtiene un token de seguridad del Servicio de token de seguridad (STS) y realiza las solicitudes sincrónicas al servicio para una operación matemática determinada. El servicio responde a continuación con el resultado. La actividad del cliente es visible en la ventana de la consola.  
  
 El ejemplo pone el contrato `ICalculator` disponible mediante el elemento `ws2007FederationHttpBinding`. La configuración de este enlace en el cliente se muestra en el código siguiente.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Endpoint address and binding for Security Token Service -->  
          <issuer address ="http://localhost:8000/sts/windows"   
                  binding ="ws2007HttpBinding" />                
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 En el [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), el `security` valor especifica que se debe usar el modo de seguridad. En este ejemplo, `message` utiliza la seguridad, que es el motivo por el [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) se especifican dentro la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md). El [ \<emisor >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) elemento dentro de la [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) especifica la dirección y el enlace para STS que emite un token de seguridad para el cliente para que el cliente pueda autenticarse en el `ICalculator` service.  
  
 La configuración de este enlace en el servicio se muestra en el código siguiente.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Metadata address for Security Token Service -->  
          <issuerMetadata address ="http://localhost:8000/sts/mex" >  
            <identity>  
              <certificateReference storeLocation ="CurrentUser"   
                                    storeName="TrustedPeople"   
                                    x509FindType ="FindBySubjectDistinguishedName"   
                                    findValue ="CN=STS" />  
            </identity>  
          </issuerMetadata>  
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 En el [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), el `security` valor especifica que se debe usar el modo de seguridad. En este ejemplo, `message` utiliza la seguridad, que es el motivo por el [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) se especifican dentro la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md). El [ \<issuerMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) elemento de `ws2007FederationHttpBinding` dentro de la [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) especifica la dirección e identidad para un punto de conexión que puede usarse para recuperar metadatos para STS.  
  
 El comportamiento para el servicio se muestra en el código siguiente.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name ="ServiceBehaviour" >  
      <serviceDebug includeExceptionDetailInFaults ="true"/>  
      <serviceMetadata httpGetEnabled ="true"/>  
      <serviceCredentials>  
        <issuedTokenAuthentication>  
          <knownCertificates>  
            <add storeLocation ="LocalMachine"  
                 storeName="TrustedPeople"  
                 x509FindType="FindBySubjectDistinguishedName"  
                 findValue="CN=STS" />  
          </knownCertificates>  
        </issuedTokenAuthentication>  
        <serviceCertificate storeLocation ="LocalMachine"  
                            storeName ="My"  
                            x509FindType ="FindBySubjectDistinguishedName"  
                            findValue ="CN=localhost"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 El [ \<issuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> permite al servicio especificar las restricciones en los tokens y permite a los clientes presentarse durante la autenticación. Esta configuración especifica que el servicio acepta los tokens firmados por un certificado cuyo nombre de asunto sea CN=STS.  
  
 STS hace que esté disponible un punto de conexión único mediante el estándar <xref:System.ServiceModel.WS2007HttpBinding>. El servicio responde a las solicitudes de los clientes para los tokens. Si el cliente se autentica utilizando una cuenta de Windows, el servicio emite un token que contiene el nombre de usuario del cliente como una demanda. Como parte de la creación del token, el STS firma el token usando la clave privada asociada con el certificado de CN=STS. Además, crea una clave simétrica y la cifra utilizando la clave pública asociada con el certificado de CN=localhost. Para devolver el token al cliente, el STS devuelve también la clave simétrica. El cliente presenta el token emitido al servicio `ICalculator` y demuestra que conoce la clave simétrica firmando el mensaje con esa clave.  
  
 Al ejecutar el ejemplo, la solicitud para el token de seguridad se muestra en la ventana de la consola del STS. Las solicitudes y respuestas de la operación se muestran en las ventanas de la consola del cliente y del servicio. Presione ENTRAR en cualquiera de las ventanas de la consola para cerrar la aplicación.  

```
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 El archivo Setup.bat incluido con este ejemplo le permite configurar el servidor y el STS con los certificados pertinentes para ejecutan una aplicación autohospedada. El archivo por lotes crea dos certificados en el almacén de certificados LocalMachine /TrustedPeople. El primer certificado tiene un nombre sujeto de CN=STS y STS lo utiliza para firmar los tokens de seguridad que emite al cliente. El segundo certificado tiene un nombre sujeto de CN=localhost y el STS lo utiliza para cifrar en cierto modo una clave que el servicio puede descifrar.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Abra un símbolo del sistema para desarrolladores de Visual Studio con privilegios de administrador y ejecute el archivo Setup.bat para crear los certificados necesarios.  
  
 Este archivo por lotes utiliza Certmgr.exe y Makecert.exe, que se distribuyen con Windows SDK. Sin embargo, debe ejecutar Setup.bat desde un símbolo del sistema de Visual Studio para que el script pueda encontrar estas herramientas.  
  
1.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md). Si usas [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], debe ejecutar Service.exe, Client.exe y SecurityTokenService.exe con privilegios elevados (haga clic en los archivos y, a continuación, haga clic en **ejecutar como administrador**).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  
  
