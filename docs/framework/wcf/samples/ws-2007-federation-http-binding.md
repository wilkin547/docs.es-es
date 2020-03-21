---
title: Enlace HTTP de federación de WS 2007
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: bf61e64733859d96adf42fbacf08266eca1f5b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183183"
---
# <a name="ws-2007-federation-http-binding"></a>Enlace HTTP de federación de WS 2007

Este ejemplo muestra el uso de <xref:System.ServiceModel.WS2007FederationHttpBinding>, un enlace estándar que puede utilizar para generar escenarios federados que admiten la versión 1.3 de la especificación WS-Trust.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

El ejemplo consta de un programa cliente basado en consola (*Client.exe*), un programa de servicio de token de seguridad basado en consola (*Securitytokenservice.exe*) y un programa de servicio basado en consola (*Service.exe*). El servicio implementa un contrato que define un patrón de comunicación de solicitud/respuesta. La interfaz `ICalculator`, que expone las operaciones matemáticas (`Add`, `Subtract`, `Multiply`y `Divide`) define el contrato. El cliente obtiene un token de seguridad del Servicio de token de seguridad (STS) y realiza las solicitudes sincrónicas al servicio para una operación matemática determinada. El servicio responde a continuación con el resultado. La actividad del cliente es visible en la ventana de la consola.

El ejemplo pone el contrato `ICalculator` disponible mediante el elemento `ws2007FederationHttpBinding`. La configuración de este enlace en el cliente se muestra en el código siguiente:

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

En [ \< ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)el>`security` de seguridad , el valor especifica qué modo de seguridad se debe utilizar. En este `message` ejemplo, se utiliza la [ \<](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) seguridad, por lo que el>de mensaje se especifica dentro de la [ \<>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)de seguridad. El [ \<elemento>del emisor](../../configure-apps/file-schema/wcf/issuer.md) dentro del `ICalculator` [ \<mensaje>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) especifica la dirección y el enlace del STS que emite un token de seguridad al cliente para que el cliente pueda autenticarse en el servicio.
  
La configuración de este enlace en el servicio se muestra en el código siguiente:

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

En [ \< ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)el>`security` de seguridad , el valor especifica qué modo de seguridad se debe utilizar. En este `message` ejemplo, se utiliza la [ \<](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) seguridad, por lo que el>de mensaje se especifica dentro de la [ \<>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)de seguridad. El [ \<elemento issuerMetadata>](../../configure-apps/file-schema/wcf/issuermetadata.md) de `ws2007FederationHttpBinding` dentro del [ \<mensaje>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) especifica la dirección y la identidad de un punto de conexión que se puede usar para recuperar metadatos para el STS.

El comportamiento del servicio se muestra en el código siguiente:

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
  
El>[ \<issuedTokenAuthentication](../../configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> permite al servicio especificar restricciones en los tokens que permite a los clientes presentar durante la autenticación. Esta configuración especifica que el servicio acepta los tokens firmados por un certificado cuyo nombre de asunto sea CN=STS.

STS hace que esté disponible un punto de conexión único mediante el estándar <xref:System.ServiceModel.WS2007HttpBinding>. El servicio responde a las solicitudes de los clientes para los tokens. Si el cliente se autentica utilizando una cuenta de Windows, el servicio emite un token que contiene el nombre de usuario del cliente como una demanda. Como parte de la creación del token, el STS firma el token usando la clave privada asociada con el certificado de CN=STS. Además, crea una clave simétrica y la cifra utilizando la clave pública asociada con el certificado de CN=localhost. Para devolver el token al cliente, el STS devuelve también la clave simétrica. El cliente presenta el token emitido al servicio `ICalculator` y demuestra que conoce la clave simétrica firmando el mensaje con esa clave.

Al ejecutar el ejemplo, la solicitud para el token de seguridad se muestra en la ventana de la consola del STS. Las solicitudes y respuestas de la operación se muestran en las ventanas de la consola del cliente y del servicio. Presione ENTRAR en cualquiera de las ventanas de la consola para cerrar la aplicación.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

El archivo *Setup.bat* incluido en este ejemplo le permite configurar el servidor y STS con los certificados relevantes para ejecutar una aplicación autohospedada. El archivo por lotes crea dos certificados en el almacén de certificados LocalMachine /TrustedPeople. El primer certificado tiene un nombre sujeto de CN=STS y STS lo utiliza para firmar los tokens de seguridad que emite al cliente. El segundo certificado tiene un nombre sujeto de CN=localhost y el STS lo utiliza para cifrar en cierto modo una clave que el servicio puede descifrar.

## <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo
  
1. Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .

2. Abra un símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecute el archivo Setup.bat para crear los certificados necesarios.

 Este archivo por lotes utiliza *Certmgr.exe* y Makecert.exe, que se distribuyen con el Windows SDK. Sin embargo, debe ejecutar *Setup.bat* desde un símbolo del sistema de Visual Studio para habilitar el script para buscar estas herramientas.

1. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

2. Para ejecutar el ejemplo en una configuración de un equipo o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](running-the-samples.md)de Windows Communication Foundation . Si utiliza Windows Vista, debe ejecutar *Service.exe*, *Client.exe*y *SecurityTokenService.exe* con privilegios elevados (haga clic con el botón derecho en los archivos y, a continuación, haga clic en **Ejecutar como administrador**).

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar:
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio:
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`
