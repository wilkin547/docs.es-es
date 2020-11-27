---
title: Procedimiento para especificar las credenciales de seguridad de los canales
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 9236985ef461044e480847003d9d249b7e232783
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266771"
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="6cf8a-102">Procedimiento para especificar las credenciales de seguridad de los canales</span><span class="sxs-lookup"><span data-stu-id="6cf8a-102">How to: Specify Channel Security Credentials</span></span>

<span data-ttu-id="6cf8a-103">El moniker del servicio Windows Communication Foundation (WCF) permite que las aplicaciones COM llamen a servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-103">The Windows Communication Foundation (WCF) Service Moniker allows COM applications to call WCF services.</span></span> <span data-ttu-id="6cf8a-104">La mayoría de los servicios WCF requieren que el cliente especifique las credenciales para la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-104">Most WCF services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="6cf8a-105">Al llamar a un servicio WCF desde un cliente WCF, puede especificar estas credenciales en código administrado o en un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-105">When calling a WCF service from a WCF client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="6cf8a-106">Al llamar a un servicio WCF desde una aplicación COM, puede usar la <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interfaz para especificar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-106">When calling a WCF service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="6cf8a-107">Este tema describe varias maneras de especificar credenciales mediante la interfaz <xref:System.ServiceModel.ComIntegration.IChannelCredentials>.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6cf8a-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> es una interfaz basada en IDispatch y no se obtiene la funcionalidad IntelliSense en el entorno de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="6cf8a-109">En este artículo se usará el servicio WCF definido en el [ejemplo de seguridad de mensajes](../samples/message-security-sample.md).</span><span class="sxs-lookup"><span data-stu-id="6cf8a-109">This article will use the WCF service defined in the [Message Security Sample](../samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="6cf8a-110">Para especificar un certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="6cf8a-110">To specify a client certificate</span></span>  
  
1. <span data-ttu-id="6cf8a-111">Ejecute el archivo Setup.bat en el directorio de seguridad del mensaje para crear e instalar los certificados de prueba necesarios.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2. <span data-ttu-id="6cf8a-112">Abra el proyecto de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-112">Open the Message Security project.</span></span>  
  
3. <span data-ttu-id="6cf8a-113">Agregue `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` a la `ICalculator` definición de interfaz.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-113">Add `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` to the `ICalculator` interface definition.</span></span>  
  
4. <span data-ttu-id="6cf8a-114">Agregue `bindingNamespace="http://Microsoft.ServiceModel.Samples"` a la etiqueta de extremo en el App.config para el servicio.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-114">Add `bindingNamespace="http://Microsoft.ServiceModel.Samples"` to the endpoint tag in the App.config for the service.</span></span>  
  
5. <span data-ttu-id="6cf8a-115">Compile el ejemplo de seguridad del mensaje y ejecute Service.exe.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="6cf8a-116">Use Internet Explorer y busque el URI del servicio ( `http://localhost:8000/ServiceModelSamples/Service` ) para asegurarse de que el servicio está funcionando.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-116">Use Internet Explorer and browse to the service's URI (`http://localhost:8000/ServiceModelSamples/Service`) to ensure that the service is working.</span></span>  
  
6. <span data-ttu-id="6cf8a-117">Abra Visual Basic 6.0 y cree un nuevo archivo .exe estándar.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="6cf8a-118">Agregue un botón al formulario y haga doble clic en él para agregar el código siguiente al controlador de clic:</span><span class="sxs-lookup"><span data-stu-id="6cf8a-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb  
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
  
7. <span data-ttu-id="6cf8a-119">Ejecute la aplicación Visual Basic y compruebe los resultados.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="6cf8a-120">La aplicación Visual Basic mostrará un cuadro de mensaje con el resultado de la llamada a Add(3, 4).</span><span class="sxs-lookup"><span data-stu-id="6cf8a-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <span data-ttu-id="6cf8a-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> o <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> también se puede usar en lugar de <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> para establecer el certificado de cliente:</span><span class="sxs-lookup"><span data-stu-id="6cf8a-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```vb  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
> <span data-ttu-id="6cf8a-122">Para que esta llamada funcione, es necesario que el equipo en el que se ejecuta el cliente confíe en el certificado del cliente.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6cf8a-123">Si el moniker es incorrecto o si el servicio no está disponible, la llamada a `GetObject` devolverá un error que dirá "Sintaxis no válida."</span><span class="sxs-lookup"><span data-stu-id="6cf8a-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="6cf8a-124">Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="6cf8a-125">Para especificar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-125">To specify user name and password</span></span>  
  
1. <span data-ttu-id="6cf8a-126">Modifique el archivo de servicio App.config para utilizar `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="6cf8a-127">Este paso es necesario para la validación del nombre de usuario y la contraseña:</span><span class="sxs-lookup"><span data-stu-id="6cf8a-127">This is required for user name and password validation:</span></span>  

2. <span data-ttu-id="6cf8a-128">Establezca `clientCredentialType` en UserName:</span><span class="sxs-lookup"><span data-stu-id="6cf8a-128">Set the `clientCredentialType` to UserName:</span></span>  

3. <span data-ttu-id="6cf8a-129">Abra Visual Basic 6.0 y cree un nuevo archivo .exe estándar.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="6cf8a-130">Agregue un botón al formulario y haga doble clic en él para agregar el código siguiente al controlador de clic:</span><span class="sxs-lookup"><span data-stu-id="6cf8a-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4. <span data-ttu-id="6cf8a-131">Ejecute la aplicación Visual Basic y compruebe los resultados.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="6cf8a-132">La aplicación Visual Basic mostrará un cuadro de mensaje con el resultado de la llamada a Add(3, 4).</span><span class="sxs-lookup"><span data-stu-id="6cf8a-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6cf8a-133">El enlace especificado en el moniker de servicio de este ejemplo se ha cambiado a WSHttpBinding_ICalculator.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="6cf8a-134">Tenga en cuenta también que debe proporcionar un nombre de usuario y contraseña validos en la llamada a <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="6cf8a-135">Para especificar las credenciales de Windows</span><span class="sxs-lookup"><span data-stu-id="6cf8a-135">To specify Windows Credentials</span></span>  
  
1. <span data-ttu-id="6cf8a-136">Establezca `clientCredentialType` en Windows en el archivo de servicio App.config:</span><span class="sxs-lookup"><span data-stu-id="6cf8a-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  

2. <span data-ttu-id="6cf8a-137">Abra Visual Basic 6.0 y cree un nuevo archivo .exe estándar.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="6cf8a-138">Agregue un botón al formulario y haga doble clic en él para agregar el código siguiente al controlador de clic:</span><span class="sxs-lookup"><span data-stu-id="6cf8a-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="6cf8a-139">Ejecute la aplicación Visual Basic y compruebe los resultados.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="6cf8a-140">La aplicación Visual Basic mostrará un cuadro de mensaje con el resultado de la llamada a Add(3, 4).</span><span class="sxs-lookup"><span data-stu-id="6cf8a-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6cf8a-141">Reemplazar "dominio", "identificación de usuario" y "contraseña" con valores válidos.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="6cf8a-142">Especificar la emisión de un token</span><span class="sxs-lookup"><span data-stu-id="6cf8a-142">To specify an issue token</span></span>  
  
1. <span data-ttu-id="6cf8a-143">Los tokens de problema solo se usan en aplicaciones que utilizan la seguridad federada.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="6cf8a-144">Para obtener más información sobre la seguridad federada, vea [Federación y tokens emitidos](federation-and-issued-tokens.md) y [ejemplo de Federación](../samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="6cf8a-144">For more information about federated security, see [Federation and Issued Tokens](federation-and-issued-tokens.md) and [Federation Sample](../samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="6cf8a-145">El siguiente ejemplo de código de Visual Basic ilustra cómo llamar al método <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```vb
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="6cf8a-146">Para obtener información acerca de los parámetros de este método, vea <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="6cf8a-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf8a-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cf8a-147">See also</span></span>

- [<span data-ttu-id="6cf8a-148">Federación</span><span class="sxs-lookup"><span data-stu-id="6cf8a-148">Federation</span></span>](federation.md)
- [<span data-ttu-id="6cf8a-149">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="6cf8a-149">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="6cf8a-150">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="6cf8a-150">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)
- [<span data-ttu-id="6cf8a-151">Seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="6cf8a-151">Message Security</span></span>](message-security-in-wcf.md)
- [<span data-ttu-id="6cf8a-152">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="6cf8a-152">Bindings and Security</span></span>](bindings-and-security.md)
