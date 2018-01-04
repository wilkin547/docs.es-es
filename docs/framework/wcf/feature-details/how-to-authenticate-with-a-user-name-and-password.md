---
title: "Cómo: Autenticar con un nombre de usuario y contraseña"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1554e8594a611aa75876d14ee7ad0689932372e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="112c9-102">Cómo: Autenticar con un nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="112c9-102">How to: Authenticate with a User Name and Password</span></span>
<span data-ttu-id="112c9-103">Este tema muestra cómo permitir a un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] autenticar un cliente con un nombre de usuario y una contraseña de un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="112c9-103">This topic demonstrates how to enable a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="112c9-104">Se supone que tiene un servicio WCF autohospedado que funciona.</span><span class="sxs-lookup"><span data-stu-id="112c9-104">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="112c9-105">Para obtener un ejemplo de creación de un vea servicio hospedado por sí mismo básico de WCF, [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="112c9-105">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="112c9-106">En este tema se supone que el servicio se configura en código.</span><span class="sxs-lookup"><span data-stu-id="112c9-106">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="112c9-107">Si le gustaría ver un ejemplo de cómo configurar un servicio similar mediante un archivo de configuración vea [nombre de usuario de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span><span class="sxs-lookup"><span data-stu-id="112c9-107">If you would like to see an example of configuring a similar service using a configuration file see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span></span>  
  
 <span data-ttu-id="112c9-108">Para configurar un servicio para autenticar a sus clientes mediante nombre de usuario y contraseñas del dominio de Windows, use el <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> y establezca su `Security.Mode` propiedad `Message`.</span><span class="sxs-lookup"><span data-stu-id="112c9-108">To configure a service to authenticate its clients using Windows Domain username and passwords use the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="112c9-109">Además debe especificar un certificado X509 que se usará para cifrar el nombre de usuario y la contraseña que se envían del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="112c9-109">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>  
  
 <span data-ttu-id="112c9-110">En el cliente, debe pedir al usuario el nombre de usuario y la contraseña y especificar las credenciales del usuario en el proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="112c9-110">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>  
  
### <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="112c9-111">Para configurar un servicio de WCF para autenticar mediante nombre de usuario y contraseña de un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="112c9-111">To configure a WCF service to authenticate using Windows domain username and password.</span></span>  
  
1.  <span data-ttu-id="112c9-112">Cree una instancia de la <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, establezca el modo de seguridad del enlace a `SecurityMode.Message`, establezca el `ClientCredentialType` del enlace a `MessageCredentialType.UserName`y agregue un extremo de servicio usando el enlace configurado al host de servicio, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="112c9-112">Create an instance of the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, set the security mode of the binding to `SecurityMode.Message`, set the `ClientCredentialType` of the binding to `MessageCredentialType.UserName`, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  <span data-ttu-id="112c9-113">Especifique el certificado de servidor usado para cifrar la información de nombre de usuario y contraseña enviada a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="112c9-113">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="112c9-114">Este código debe seguir inmediatamente al código anterior.</span><span class="sxs-lookup"><span data-stu-id="112c9-114">This code should immediately follow the code above.</span></span> <span data-ttu-id="112c9-115">En el ejemplo siguiente se utiliza el certificado que se creó el archivo setup.bat desde la [nombre de usuario de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-user-name.md) ejemplo:</span><span class="sxs-lookup"><span data-stu-id="112c9-115">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md) sample:</span></span>  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     <span data-ttu-id="112c9-116">Puede usar su propio certificado; simplemente modifique el código para hacer referencia al certificado.</span><span class="sxs-lookup"><span data-stu-id="112c9-116">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="112c9-117">Para obtener más información sobre la creación y uso de certificados, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="112c9-117">For more information about creating and using certificates see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="112c9-118">Asegúrese de que el certificado está en el almacén de certificados Personas de confianza del equipo local.</span><span class="sxs-lookup"><span data-stu-id="112c9-118">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="112c9-119">Puede hacerlo ejecutando mmc.exe y seleccionando la **archivo**, **agregar o quitar complemento...**  elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="112c9-119">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="112c9-120">En el **agregar o quitar complementos** cuadro de diálogo, seleccione la **complemento certificados** y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="112c9-120">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="112c9-121">En el cuadro de diálogo complemento de certificados seleccione **cuenta de equipo**.</span><span class="sxs-lookup"><span data-stu-id="112c9-121">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="112c9-122">De forma predeterminada el certificado generado por el ejemplo de Nombre de usuario de seguridad de mensaje se encuentra en la carpeta Personal/Certificados.</span><span class="sxs-lookup"><span data-stu-id="112c9-122">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="112c9-123">Se enumerarán como "localhost" en la columna emitido para en la ventana de MMC.</span><span class="sxs-lookup"><span data-stu-id="112c9-123">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="112c9-124">Arrastre y coloque el certificado en el **personas de confianza** carpeta.</span><span class="sxs-lookup"><span data-stu-id="112c9-124">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="112c9-125">Esto permitirá a WCF tratar el certificado como certificado de confianza al realizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="112c9-125">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>  
  
### <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="112c9-126">Para llamar al servicio pasando el nombre de usuario y la contraseña</span><span class="sxs-lookup"><span data-stu-id="112c9-126">To call the service passing username and password</span></span>  
  
1.  <span data-ttu-id="112c9-127">La aplicación cliente debe pedir al usuario su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="112c9-127">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="112c9-128">El siguiente código pide al usuario el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="112c9-128">The following code asks the user for username and password.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="112c9-129">Este código no se debe usar en producción porque se muestra la contraseña mientras se está escribiendo.</span><span class="sxs-lookup"><span data-stu-id="112c9-129">This code should not be used in production as the password is displayed while being entered.</span></span>  
  
    ```  
    public static void GetPassword(out string username, out string password)  
            {  
                Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");  
                Console.WriteLine("   Enter username:");  
                username = Console.ReadLine();  
                Console.WriteLine("   Enter password:");  
                password = Console.ReadLine();             
                return;  
            }  
    ```  
  
2.  <span data-ttu-id="112c9-130">Cree una instancia del proxy de cliente que especifique las credenciales del cliente tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="112c9-130">Create an instance of the client proxy specifying the client’s credentials as shown in the following code:</span></span>  
  
    ```  
    string username;  
    string password;  
  
    // Instantiate the proxy  
    Service1Client proxy = new Service1Client();  
  
    // Prompt the user for username & password  
    GetPassword(out username, out password);  
  
    // Set the user’s credentials on the proxy  
    proxy.ClientCredentials.UserName.UserName = username;  
    proxy.ClientCredentials.UserName.Password = password;  
  
    // Treat the test certificate as trusted  
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;  
    // Call the service operation using the proxy  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="112c9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="112c9-131">See Also</span></span>  
 <span data-ttu-id="112c9-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="112c9-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [<span data-ttu-id="112c9-133">Seguridad del transporte con la autenticación básica</span><span class="sxs-lookup"><span data-stu-id="112c9-133">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [<span data-ttu-id="112c9-134">Seguridad distribuida de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="112c9-134">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="112c9-135">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="112c9-135">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
