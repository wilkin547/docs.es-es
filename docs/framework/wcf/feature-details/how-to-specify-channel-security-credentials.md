---
title: Procedimiento para especificar las credenciales de seguridad de los canales
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 0bfbb71ade3822b9f504c2f89a41145ce0d435f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297985"
---
# <a name="how-to-specify-channel-security-credentials"></a>Procedimiento para especificar las credenciales de seguridad de los canales
El Moniker de servicio de Windows Communication Foundation (WCF) permite a las aplicaciones COM llamar a los servicios WCF. La mayoría de los servicios WCF requieren que el cliente especificar las credenciales para la autenticación y autorización. Al llamar a un servicio WCF desde un cliente WCF, puede especificar estas credenciales en código administrado o en un archivo de configuración de la aplicación. Al llamar a un servicio WCF desde una aplicación COM, puede usar el <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interfaz para especificar las credenciales. Este tema describe varias maneras de especificar credenciales mediante la interfaz <xref:System.ServiceModel.ComIntegration.IChannelCredentials>.  
  
> [!NOTE]
>  <xref:System.ServiceModel.ComIntegration.IChannelCredentials> es una interfaz basada en IDispatch y no se obtiene la funcionalidad IntelliSense en el entorno de Visual Studio.  
  
 Este artículo utiliza el servicio WCF definido en el [ejemplo de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-sample.md).  
  
### <a name="to-specify-a-client-certificate"></a>Para especificar un certificado de cliente  
  
1. Ejecute el archivo Setup.bat en el directorio de seguridad del mensaje para crear e instalar los certificados de prueba necesarios.  
  
2. Abra el proyecto de seguridad del mensaje.  
  
3. Agregar `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` a la `ICalculator` definición de interfaz.  
  
4. Agregar `bindingNamespace="http://Microsoft.ServiceModel.Samples"` a la etiqueta de punto de conexión en el archivo App.config para el servicio.  
  
5. Compile el ejemplo de seguridad del mensaje y ejecute Service.exe. Utilice Internet Explorer y vaya al URI del servicio (http://localhost:8000/ServiceModelSamples/Service) para asegurarse de que el servicio está funcionando.  
  
6. Abra Visual Basic 6.0 y cree un nuevo archivo .exe estándar. Agregue un botón al formulario y haga doble clic en él para agregar el código siguiente al controlador de clic:  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7. Ejecute la aplicación Visual Basic y compruebe los resultados.  
  
     La aplicación Visual Basic mostrará un cuadro de mensaje con el resultado de la llamada a Add(3, 4). <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> o <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> también se puede usar en lugar de <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> para establecer el certificado de cliente:  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
>  Para que esta llamada funcione, es necesario que el equipo en el que se ejecuta el cliente confíe en el certificado del cliente.  
  
> [!NOTE]
>  Si el moniker es incorrecto o si el servicio no está disponible, la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida." Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.  
  
### <a name="to-specify-user-name-and-password"></a>Para especificar un nombre de usuario y una contraseña.  
  
1. Modifique el archivo de servicio App.config para utilizar `wsHttpBinding`. Este paso es necesario para la validación del nombre de usuario y la contraseña:  

2. Establezca `clientCredentialType` en UserName:  

3. Abra Visual Basic 6.0 y cree un nuevo archivo .exe estándar. Agregue un botón al formulario y haga doble clic en él para agregar el código siguiente al controlador de clic:  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4. Ejecute la aplicación Visual Basic y compruebe los resultados. La aplicación Visual Basic mostrará un cuadro de mensaje con el resultado de la llamada a Add(3, 4).  
  
    > [!NOTE]
    >  El enlace especificado en el moniker de servicio de este ejemplo se ha cambiado a WSHttpBinding_ICalculator. Tenga en cuenta también que debe proporcionar un nombre de usuario y contraseña validos en la llamada a <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.  
  
### <a name="to-specify-windows-credentials"></a>Para especificar las credenciales de Windows  
  
1. Establezca `clientCredentialType` en Windows en el archivo de servicio App.config:  

2. Abra Visual Basic 6.0 y cree un nuevo archivo .exe estándar. Agregue un botón al formulario y haga doble clic en él para agregar el código siguiente al controlador de clic:  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3. Ejecute la aplicación Visual Basic y compruebe los resultados. La aplicación Visual Basic mostrará un cuadro de mensaje con el resultado de la llamada a Add(3, 4).  
  
    > [!NOTE]
    >  Reemplazar "dominio", "identificación de usuario" y "contraseña" con valores válidos.  
  
### <a name="to-specify-an-issue-token"></a>Especificar la emisión de un token  
  
1. Los tokens de problema solo se usan en aplicaciones que utilizan la seguridad federada. Para obtener más información acerca de la seguridad federada, vea [federación y Tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) y [ejemplo de federación](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
     El siguiente ejemplo de código de Visual Basic ilustra cómo llamar al método <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     Para obtener información acerca de los parámetros de este método, vea <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.  
  
## <a name="see-also"></a>Vea también

- [Federación](../../../../docs/framework/wcf/feature-details/federation.md)
- [Cómo: Configurar las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Cómo: Crear a un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Seguridad de los mensajes](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [Enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
