---
title: Procedimiento para hospedar un servicio WCF en una aplicación administrada
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 131d99457427e0818f78076d987f550a99ad7cf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929316"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="7738e-102">Procedimiento Hospedar un servicio WCF en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="7738e-102">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="7738e-103">Para hospedar un servicio dentro de una aplicación administrada, incruste el código del servicio dentro del código de la aplicación administrada, defina un extremo para el servicio de manera imperativa mediante código, de manera declarativa mediante configuración o usando extremos predeterminados y, a continuación, cree una instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7738e-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="7738e-104">Para comenzar a recibir mensajes, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7738e-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="7738e-105">Esto crea y abre el agente de escucha del servicio.</span><span class="sxs-lookup"><span data-stu-id="7738e-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="7738e-106">Hospedar un servicio de esta manera se conoce a menudo como "autohospedaje", puesto que la aplicación administrada está haciendo el propio trabajo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="7738e-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="7738e-107">Para cerrar el servicio, llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7738e-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="7738e-108">Un servicio también se puede hospedar en un servicio de Windows administrado, en Internet Information Services (IIS) o en Servicio de activación de procesos de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="7738e-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="7738e-109">Para obtener más información acerca de las opciones para un servicio de hospedaje, vea [servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="7738e-109">For more information about hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>

<span data-ttu-id="7738e-110">Hospedar un servicio en una aplicación administrada es la opción más flexible porque es la que necesita una menor infraestructura para su implementación.</span><span class="sxs-lookup"><span data-stu-id="7738e-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="7738e-111">Para obtener más información sobre el hospedaje de servicios en las aplicaciones administradas, vea [hospedaje en una aplicación administrada](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="7738e-111">For more information about hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="7738e-112">El siguiente procedimiento muestra cómo implementar un servicio autohospedado en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="7738e-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="7738e-113">Crear un servicio autohospedado</span><span class="sxs-lookup"><span data-stu-id="7738e-113">Create a self-hosted service</span></span>

1. <span data-ttu-id="7738e-114">Cree una nueva aplicación de consola:</span><span class="sxs-lookup"><span data-stu-id="7738e-114">Create a new console application:</span></span>

   1. <span data-ttu-id="7738e-115">Abra Visual Studio y seleccione **New** > **proyecto** desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="7738e-115">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="7738e-116">En el **plantillas instaladas** lista, seleccione **Visual C#** o **Visual Basic**y, a continuación, seleccione **Windows Desktop**.</span><span class="sxs-lookup"><span data-stu-id="7738e-116">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="7738e-117">Seleccione el **aplicación de consola** plantilla.</span><span class="sxs-lookup"><span data-stu-id="7738e-117">Select the **Console App** template.</span></span> <span data-ttu-id="7738e-118">Tipo `SelfHost` en el **nombre** cuadro y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7738e-118">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="7738e-119">Haga clic en **SelfHost** en **el Explorador de soluciones** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="7738e-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="7738e-120">Seleccione **System.ServiceModel** desde el **.NET** ficha y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7738e-120">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="7738e-121">Si el **el Explorador de soluciones** ventana no está visible, seleccione **el Explorador de soluciones** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="7738e-121">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="7738e-122">Haga doble clic en **Program.cs** o **Module1.vb** en **el Explorador de soluciones** para abrirlo en la ventana de código, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="7738e-122">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="7738e-123">Agregue las siguientes instrucciones en la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="7738e-123">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="7738e-124">Defina e implemente un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="7738e-124">Define and implement a service contract.</span></span> <span data-ttu-id="7738e-125">En este ejemplo se define un `HelloWorldService` que devuelve un mensaje en función de la entrada al servicio.</span><span class="sxs-lookup"><span data-stu-id="7738e-125">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="7738e-126">Para obtener más información acerca de cómo definir e implementar una interfaz de servicio, vea [Cómo: Definir un contrato de servicio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) y [Cómo: Implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="7738e-126">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="7738e-127">Al principio del método `Main`, cree una instancia de la clase <xref:System.Uri> con la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="7738e-127">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="7738e-128">Cree una instancia de la clase <xref:System.ServiceModel.ServiceHost>, pasando un <xref:System.Type> que representa el tipo de servicio y el Identificador uniforme de recursos (URI) de la dirección base al <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="7738e-128">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="7738e-129">Habilite la publicación de metadatos y, a continuación, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost> para inicializar el servicio y prepararlo para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="7738e-129">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="7738e-130">En este ejemplo se usan puntos de conexión predeterminados, y este servicio no requiere ningún archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7738e-130">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="7738e-131">Si no se configura ningún extremo, el tiempo de ejecución crea uno para cada dirección base de cada contrato de servicio implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="7738e-131">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="7738e-132">Para obtener más información sobre los puntos de conexión predeterminados, consulte [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7738e-132">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="7738e-133">Presione **Ctrl**+**MAYÚS**+**B** para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="7738e-133">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="7738e-134">Probar el servicio</span><span class="sxs-lookup"><span data-stu-id="7738e-134">Test the service</span></span>

1. <span data-ttu-id="7738e-135">Presione **Ctrl**+**F5** para ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="7738e-135">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="7738e-136">Abra **cliente de prueba WCF**.</span><span class="sxs-lookup"><span data-stu-id="7738e-136">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="7738e-137">Para abrir **cliente de prueba WCF**, abra el símbolo del sistema para desarrolladores para Visual Studio y ejecute **WcfTestClient.exe**.</span><span class="sxs-lookup"><span data-stu-id="7738e-137">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="7738e-138">Seleccione **Agregar servicio** desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="7738e-138">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="7738e-139">Tipo `http://localhost:8080/hello` en el cuadro de dirección y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7738e-139">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="7738e-140">Asegúrese de que el servicio se está ejecutando; de lo contrario, este paso producirá un error.</span><span class="sxs-lookup"><span data-stu-id="7738e-140">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="7738e-141">Si ha cambiado la dirección base en el código, use dicha dirección en este paso.</span><span class="sxs-lookup"><span data-stu-id="7738e-141">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="7738e-142">Haga doble clic en **SayHello** bajo el **Mis proyectos de servicios** nodo.</span><span class="sxs-lookup"><span data-stu-id="7738e-142">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="7738e-143">Escriba su nombre en el **valor** columna en el **solicitar** lista y haga clic en **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="7738e-143">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="7738e-144">Aparece un mensaje de respuesta en el **respuesta** lista.</span><span class="sxs-lookup"><span data-stu-id="7738e-144">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="7738e-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7738e-145">Example</span></span>

<span data-ttu-id="7738e-146">El siguiente ejemplo crea un objeto <xref:System.ServiceModel.ServiceHost> para hospedar un servicio de tipo `HelloWorldService`, y, a continuación, llama al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7738e-146">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="7738e-147">Se proporciona una dirección base mediante código, se habilita la publicación de metadatos y se usan extremos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="7738e-147">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="7738e-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="7738e-148">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="7738e-149">Cómo: Hospedar un servicio WCF en IIS</span><span class="sxs-lookup"><span data-stu-id="7738e-149">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="7738e-150">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="7738e-150">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="7738e-151">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7738e-151">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="7738e-152">Cómo: Definir un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="7738e-152">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="7738e-153">Cómo: Implementar un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="7738e-153">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="7738e-154">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="7738e-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="7738e-155">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7738e-155">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7738e-156">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="7738e-156">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)