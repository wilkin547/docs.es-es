---
title: Procedimiento para autenticar con un nombre de usuario y contraseña
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: e8dc9177afc590a6467855decfa8450b37c6fc77
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601288"
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="63bfd-102">Procedimiento para autenticar con un nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="63bfd-102">How to: Authenticate with a User Name and Password</span></span>

<span data-ttu-id="63bfd-103">En este tema se muestra cómo habilitar un servicio de Windows Communication Foundation (WCF) para autenticar un cliente con un nombre de usuario y una contraseña de dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="63bfd-103">This topic demonstrates how to enable a Windows Communication Foundation (WCF) service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="63bfd-104">Se supone que tiene un servicio WCF autohospedado que funciona.</span><span class="sxs-lookup"><span data-stu-id="63bfd-104">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="63bfd-105">Para obtener un ejemplo de cómo crear un servicio WCF básico autohospedado, vea [Introducción tutorial](../getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="63bfd-105">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="63bfd-106">En este tema se supone que el servicio se configura en código.</span><span class="sxs-lookup"><span data-stu-id="63bfd-106">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="63bfd-107">Si desea ver un ejemplo de configuración de un servicio similar mediante un archivo de configuración, vea [nombre de usuario de seguridad de mensaje](../samples/message-security-user-name.md).</span><span class="sxs-lookup"><span data-stu-id="63bfd-107">If you would like to see an example of configuring a similar service using a configuration file, see [Message Security User Name](../samples/message-security-user-name.md).</span></span>

<span data-ttu-id="63bfd-108">Para configurar un servicio para autenticar a sus clientes mediante nombre de usuario y contraseñas de dominio Windows, use <xref:System.ServiceModel.WSHttpBinding> y establezca su propiedad `Security.Mode` en `Message`.</span><span class="sxs-lookup"><span data-stu-id="63bfd-108">To configure a service to authenticate its clients using Windows Domain username and passwords use the <xref:System.ServiceModel.WSHttpBinding> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="63bfd-109">Además debe especificar un certificado X509 que se usará para cifrar el nombre de usuario y la contraseña que se envían del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="63bfd-109">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>

<span data-ttu-id="63bfd-110">En el cliente, debe pedir al usuario el nombre de usuario y la contraseña y especificar las credenciales del usuario en el proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="63bfd-110">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>

## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="63bfd-111">Para configurar un servicio WCF para autenticarse con el nombre de usuario y la contraseña de dominio de Windows</span><span class="sxs-lookup"><span data-stu-id="63bfd-111">To configure a WCF service to authenticate using Windows domain username and password</span></span>

1. <span data-ttu-id="63bfd-112">Cree una instancia de <xref:System.ServiceModel.WSHttpBinding>, establezca el modo de seguridad del enlace en <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, establezca el `ClientCredentialType` del enlace en <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType> y agregue un extremo de servicio usando el enlace configurado al host del servicio tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="63bfd-112">Create an instance of the <xref:System.ServiceModel.WSHttpBinding>, set the security mode of the binding to <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, set the `ClientCredentialType` of the binding to <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType>, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>

    ```csharp
    // ...
    var userNameBinding = new WSHttpBinding();
    userNameBinding.Security.Mode = SecurityMode.Message;
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");
    // ...
    ```

2. <span data-ttu-id="63bfd-113">Especifique el certificado de servidor usado para cifrar la información de nombre de usuario y contraseña enviada a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="63bfd-113">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="63bfd-114">Este código debe seguir inmediatamente al código anterior.</span><span class="sxs-lookup"><span data-stu-id="63bfd-114">This code should immediately follow the code above.</span></span> <span data-ttu-id="63bfd-115">En el ejemplo siguiente se usa el certificado creado por el archivo Setup. bat del ejemplo de [nombre de usuario de seguridad de mensaje](../samples/message-security-user-name.md) :</span><span class="sxs-lookup"><span data-stu-id="63bfd-115">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../samples/message-security-user-name.md) sample:</span></span>

    ```csharp
    // ...
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");
    // ...
    ```

    <span data-ttu-id="63bfd-116">Puede usar su propio certificado; simplemente modifique el código para hacer referencia al certificado.</span><span class="sxs-lookup"><span data-stu-id="63bfd-116">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="63bfd-117">Para obtener más información acerca de la creación y el uso de certificados, consulte [trabajar con certificados](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="63bfd-117">For more information about creating and using certificates see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="63bfd-118">Asegúrese de que el certificado está en el almacén de certificados Personas de confianza del equipo local.</span><span class="sxs-lookup"><span data-stu-id="63bfd-118">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="63bfd-119">Para ello, ejecute MMC. exe y seleccione el elemento de menú **archivo**, **Agregar o quitar complemento..** ..</span><span class="sxs-lookup"><span data-stu-id="63bfd-119">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="63bfd-120">En el cuadro de diálogo **Agregar o quitar complementos** , seleccione el **complemento certificados** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="63bfd-120">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="63bfd-121">En el cuadro de diálogo complemento certificados, seleccione **cuenta de equipo**.</span><span class="sxs-lookup"><span data-stu-id="63bfd-121">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="63bfd-122">De forma predeterminada el certificado generado por el ejemplo de Nombre de usuario de seguridad de mensaje se encuentra en la carpeta Personal/Certificados.</span><span class="sxs-lookup"><span data-stu-id="63bfd-122">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="63bfd-123">Se mostrará como "localhost" en la columna emitido para de la ventana de MMC.</span><span class="sxs-lookup"><span data-stu-id="63bfd-123">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="63bfd-124">Arrastre y coloque el certificado en la carpeta **personas de confianza** .</span><span class="sxs-lookup"><span data-stu-id="63bfd-124">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="63bfd-125">Esto permitirá a WCF tratar el certificado como certificado de confianza al realizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="63bfd-125">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>

## <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="63bfd-126">Para llamar al servicio pasando el nombre de usuario y la contraseña</span><span class="sxs-lookup"><span data-stu-id="63bfd-126">To call the service passing username and password</span></span>

1. <span data-ttu-id="63bfd-127">La aplicación cliente debe pedir al usuario su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="63bfd-127">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="63bfd-128">En el código siguiente se pide al usuario el nombre de usuario y la contraseña:</span><span class="sxs-lookup"><span data-stu-id="63bfd-128">The following code asks the user for username and password:</span></span>

    > [!WARNING]
    > <span data-ttu-id="63bfd-129">Este código no se debe usar en producción porque se muestra la contraseña mientras se está escribiendo.</span><span class="sxs-lookup"><span data-stu-id="63bfd-129">This code should not be used in production as the password is displayed while being entered.</span></span>

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

2. <span data-ttu-id="63bfd-130">Cree una instancia del proxy de cliente que especifique las credenciales del cliente, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="63bfd-130">Create an instance of the client proxy specifying the client's credentials as shown in the following code:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="63bfd-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="63bfd-131">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.SecurityMode>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>
- [<span data-ttu-id="63bfd-132">Seguridad de transporte con autenticación básica</span><span class="sxs-lookup"><span data-stu-id="63bfd-132">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)
- [<span data-ttu-id="63bfd-133">Seguridad distribuida de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="63bfd-133">Distributed Application Security</span></span>](distributed-application-security.md)
- [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)
