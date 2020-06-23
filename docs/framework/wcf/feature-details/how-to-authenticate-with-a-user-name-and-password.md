---
title: Procedimiento para autenticar con un nombre de usuario y contraseña
description: Obtenga información sobre cómo habilitar un servicio WCF para autenticar un cliente mediante el uso de un nombre de usuario y una contraseña de dominio de Windows, con código de ejemplo.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: 1f938f8041b2577b3705266948f29b42f23a6fd7
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247252"
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a>Procedimiento para autenticar con un nombre de usuario y contraseña

En este tema se muestra cómo habilitar un servicio de Windows Communication Foundation (WCF) para autenticar un cliente con un nombre de usuario y una contraseña de dominio de Windows. Se supone que tiene un servicio WCF autohospedado que funciona. Para obtener un ejemplo de cómo crear un servicio WCF básico autohospedado, vea [Introducción tutorial](../getting-started-tutorial.md). En este tema se supone que el servicio se configura en código. Si desea ver un ejemplo de configuración de un servicio similar mediante un archivo de configuración, vea [nombre de usuario de seguridad de mensaje](../samples/message-security-user-name.md).

Para configurar un servicio para autenticar a sus clientes mediante nombre de usuario y contraseñas de dominio Windows, use <xref:System.ServiceModel.WSHttpBinding> y establezca su propiedad `Security.Mode` en `Message`. Además debe especificar un certificado X509 que se usará para cifrar el nombre de usuario y la contraseña que se envían del cliente al servicio.

En el cliente, debe pedir al usuario el nombre de usuario y la contraseña y especificar las credenciales del usuario en el proxy de cliente de WCF.

## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a>Para configurar un servicio WCF para autenticarse con el nombre de usuario y la contraseña de dominio de Windows

1. Cree una instancia de <xref:System.ServiceModel.WSHttpBinding>, establezca el modo de seguridad del enlace en <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, establezca el `ClientCredentialType` del enlace en <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType> y agregue un extremo de servicio usando el enlace configurado al host del servicio tal y como se muestra en el código siguiente:

    ```csharp
    // ...
    var userNameBinding = new WSHttpBinding();
    userNameBinding.Security.Mode = SecurityMode.Message;
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");
    // ...
    ```

2. Especifique el certificado de servidor usado para cifrar la información de nombre de usuario y contraseña enviada a través de la conexión. Este código debe seguir inmediatamente al código anterior. En el ejemplo siguiente se usa el certificado creado por el archivo setup.bat del ejemplo de [nombre de usuario de seguridad de mensaje](../samples/message-security-user-name.md) :

    ```csharp
    // ...
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");
    // ...
    ```

    Puede usar su propio certificado; simplemente modifique el código para hacer referencia al certificado. Para obtener más información acerca de la creación y el uso de certificados, consulte [trabajar con certificados](working-with-certificates.md). Asegúrese de que el certificado está en el almacén de certificados Personas de confianza del equipo local. Para ello, ejecute mmc.exe y seleccione el elemento de menú **archivo**, **Agregar o quitar complemento...** . En el cuadro de diálogo **Agregar o quitar complementos** , seleccione el **complemento certificados** y haga clic en **Agregar**. En el cuadro de diálogo complemento certificados, seleccione **cuenta de equipo**. De forma predeterminada el certificado generado por el ejemplo de Nombre de usuario de seguridad de mensaje se encuentra en la carpeta Personal/Certificados.  Se mostrará como "localhost" en la columna emitido para de la ventana de MMC. Arrastre y coloque el certificado en la carpeta **personas de confianza** . Esto permitirá a WCF tratar el certificado como certificado de confianza al realizar la autenticación.

## <a name="to-call-the-service-passing-username-and-password"></a>Para llamar al servicio pasando el nombre de usuario y la contraseña

1. La aplicación cliente debe pedir al usuario su nombre de usuario y contraseña. En el código siguiente se pide al usuario el nombre de usuario y la contraseña:

    > [!WARNING]
    > Este código no se debe usar en producción porque se muestra la contraseña mientras se está escribiendo.

    ```csharp
    public static void GetPassword(out string username, out string password)
    {
        Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");
        Console.WriteLine("   Enter username:");
        username = Console.ReadLine();
        Console.WriteLine("   Enter password:");
        password = Console.ReadLine();
    }
    ```

2. Cree una instancia del proxy de cliente que especifique las credenciales del cliente, tal como se muestra en el código siguiente:

    ```csharp
    string username;
    string password;

    // Instantiate the proxy.
    var proxy = new Service1Client();

    // Prompt the user for username & password.
    GetPassword(out username, out password);

    // Set the user's credentials on the proxy.
    proxy.ClientCredentials.UserName.UserName = username;
    proxy.ClientCredentials.UserName.Password = password;

    // Treat the test certificate as trusted.
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;
    // Call the service operation using the proxy
    ```

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.SecurityMode>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>
- [Seguridad de transporte con autenticación básica](transport-security-with-basic-authentication.md)
- [Seguridad distribuida de aplicaciones](distributed-application-security.md)
- [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)
