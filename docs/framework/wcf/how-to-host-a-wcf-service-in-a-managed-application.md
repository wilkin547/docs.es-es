---
title: Procedimiento para hospedar un servicio WCF en una aplicación administrada
description: Obtenga información acerca de cómo hospedar un servicio WCF dentro de una aplicación administrada mediante la creación de un servicio autohospedado y su prueba.
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 7d1d61b683f60a6c643d2a2f03d367a6ae6c6c15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246173"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="4a462-103">Cómo: hospedar un servicio WCF en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="4a462-103">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="4a462-104">Para hospedar un servicio dentro de una aplicación administrada, incruste el código del servicio dentro del código de la aplicación administrada, defina un extremo para el servicio de manera imperativa mediante código, de manera declarativa mediante configuración o usando extremos predeterminados y, a continuación, cree una instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4a462-104">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="4a462-105">Para comenzar a recibir mensajes, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4a462-105">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="4a462-106">Esto crea y abre el agente de escucha del servicio.</span><span class="sxs-lookup"><span data-stu-id="4a462-106">This creates and opens the listener for the service.</span></span> <span data-ttu-id="4a462-107">Hospedar un servicio de esta manera se conoce a menudo como "autohospedaje", puesto que la aplicación administrada está haciendo el propio trabajo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="4a462-107">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="4a462-108">Para cerrar el servicio, llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4a462-108">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="4a462-109">Un servicio también se puede hospedar en un servicio de Windows administrado, en Internet Information Services (IIS) o en Servicio de activación de procesos de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="4a462-109">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="4a462-110">Para obtener más información sobre las opciones de hospedaje de un servicio, vea [servicios de hospedaje](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="4a462-110">For more information about hosting options for a service, see [Hosting Services](hosting-services.md).</span></span>

<span data-ttu-id="4a462-111">Hospedar un servicio en una aplicación administrada es la opción más flexible porque es la que necesita una menor infraestructura para su implementación.</span><span class="sxs-lookup"><span data-stu-id="4a462-111">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="4a462-112">Para obtener más información sobre cómo hospedar servicios en aplicaciones administradas, consulte [hospedaje en una aplicación administrada](./feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="4a462-112">For more information about hosting services in managed applications, see [Hosting in a Managed Application](./feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="4a462-113">El siguiente procedimiento muestra cómo implementar un servicio autohospedado en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="4a462-113">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="4a462-114">Crear un servicio autohospedado</span><span class="sxs-lookup"><span data-stu-id="4a462-114">Create a self-hosted service</span></span>

1. <span data-ttu-id="4a462-115">Cree una nueva aplicación de consola:</span><span class="sxs-lookup"><span data-stu-id="4a462-115">Create a new console application:</span></span>

   1. <span data-ttu-id="4a462-116">Abra Visual Studio y seleccione **nuevo**  >  **proyecto** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="4a462-116">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="4a462-117">En la lista **plantillas instaladas** , seleccione **Visual C#** o **Visual Basic**y, a continuación, seleccione **escritorio de Windows**.</span><span class="sxs-lookup"><span data-stu-id="4a462-117">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="4a462-118">Seleccione la plantilla **aplicación de consola** .</span><span class="sxs-lookup"><span data-stu-id="4a462-118">Select the **Console App** template.</span></span> <span data-ttu-id="4a462-119">Escriba `SelfHost` en el cuadro **nombre** y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4a462-119">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="4a462-120">Haga clic con el botón secundario en **SelfHost** en **Explorador de soluciones** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="4a462-120">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="4a462-121">Seleccione **System. ServiceModel** en la pestaña **.net** y, después, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4a462-121">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4a462-122">Si la ventana de **Explorador de soluciones** no está visible, seleccione **Explorador de soluciones** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="4a462-122">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="4a462-123">Haga doble clic en **Program.CS** o **Module1. VB** en **Explorador de soluciones** para abrirlo en la ventana de código, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="4a462-123">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="4a462-124">Agregue las siguientes instrucciones en la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="4a462-124">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="4a462-125">Defina e implemente un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="4a462-125">Define and implement a service contract.</span></span> <span data-ttu-id="4a462-126">En este ejemplo se define un `HelloWorldService` que devuelve un mensaje en función de la entrada al servicio.</span><span class="sxs-lookup"><span data-stu-id="4a462-126">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="4a462-127">Para obtener más información sobre cómo definir e implementar una interfaz de servicio, vea [Cómo: definir un contrato de servicio](how-to-define-a-wcf-service-contract.md) y [Cómo: implementar un contrato de servicio](how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="4a462-127">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="4a462-128">Al principio del método `Main`, cree una instancia de la clase <xref:System.Uri> con la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="4a462-128">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="4a462-129">Cree una instancia de la clase <xref:System.ServiceModel.ServiceHost>, pasando un <xref:System.Type> que representa el tipo de servicio y el Identificador uniforme de recursos (URI) de la dirección base al <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="4a462-129">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="4a462-130">Habilite la publicación de metadatos y, a continuación, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost> para inicializar el servicio y prepararlo para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="4a462-130">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="4a462-131">En este ejemplo se usan puntos de conexión predeterminados, y este servicio no requiere ningún archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4a462-131">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="4a462-132">Si no se configura ningún extremo, el tiempo de ejecución crea uno para cada dirección base de cada contrato de servicio implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="4a462-132">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="4a462-133">Para obtener más información sobre los puntos de conexión predeterminados, vea [configuración simplificada](simplified-configuration.md) y [configuración simplificada para servicios WCF](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="4a462-133">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="4a462-134">Presione **Ctrl** + **MAYÚS** + **B** para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="4a462-134">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="4a462-135">Probar el servicio</span><span class="sxs-lookup"><span data-stu-id="4a462-135">Test the service</span></span>

1. <span data-ttu-id="4a462-136">Presione **Ctrl** + **F5** para ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="4a462-136">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="4a462-137">Abra el **cliente de prueba WCF**.</span><span class="sxs-lookup"><span data-stu-id="4a462-137">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4a462-138">Para abrir el **cliente de prueba WCF**, abra símbolo del sistema para desarrolladores para Visual Studio y ejecute **WcfTestClient.exe**.</span><span class="sxs-lookup"><span data-stu-id="4a462-138">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="4a462-139">Seleccione **Agregar servicio** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="4a462-139">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="4a462-140">Escriba `http://localhost:8080/hello` en el cuadro Dirección y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4a462-140">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4a462-141">Asegúrese de que el servicio se está ejecutando; de lo contrario, este paso producirá un error.</span><span class="sxs-lookup"><span data-stu-id="4a462-141">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="4a462-142">Si ha cambiado la dirección base en el código, use dicha dirección en este paso.</span><span class="sxs-lookup"><span data-stu-id="4a462-142">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="4a462-143">Haga doble clic en **SayHello** en el nodo **mis proyectos de servicio** .</span><span class="sxs-lookup"><span data-stu-id="4a462-143">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="4a462-144">Escriba su nombre en la columna **valor** de la lista **solicitud** y haga clic en **invocar**.</span><span class="sxs-lookup"><span data-stu-id="4a462-144">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="4a462-145">Aparece un mensaje de respuesta en la lista de **respuestas** .</span><span class="sxs-lookup"><span data-stu-id="4a462-145">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="4a462-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a462-146">Example</span></span>

<span data-ttu-id="4a462-147">El siguiente ejemplo crea un objeto <xref:System.ServiceModel.ServiceHost> para hospedar un servicio de tipo `HelloWorldService`, y, a continuación, llama al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4a462-147">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="4a462-148">Se proporciona una dirección base mediante código, se habilita la publicación de metadatos y se usan extremos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="4a462-148">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="4a462-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a462-149">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="4a462-150">Procedimiento para hospedar un servicio WCF en IIS</span><span class="sxs-lookup"><span data-stu-id="4a462-150">How to: Host a WCF Service in IIS</span></span>](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="4a462-151">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="4a462-151">Self-Host</span></span>](./samples/self-host.md)
- [<span data-ttu-id="4a462-152">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4a462-152">Hosting Services</span></span>](hosting-services.md)
- [<span data-ttu-id="4a462-153">Cómo definir un contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="4a462-153">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="4a462-154">Cómo implementar un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="4a462-154">How to: Implement a Service Contract</span></span>](how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="4a462-155">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="4a462-155">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="4a462-156">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="4a462-156">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4a462-157">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="4a462-157">System-Provided Bindings</span></span>](system-provided-bindings.md)
