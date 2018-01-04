---
title: "Hospedaje de un servicio WCF en una aplicación administrada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
caps.latest.revision: "42"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6491faa6134c1e80e07294d8f888200c04fa8704
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-host-a-wcf-service-in-a-managed-application"></a><span data-ttu-id="c3ed3-102">Hospedaje de un servicio WCF en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="c3ed3-102">How to: Host a WCF Service in a Managed Application</span></span>
<span data-ttu-id="c3ed3-103">Para hospedar un servicio dentro de una aplicación administrada, incruste el código del servicio dentro del código de la aplicación administrada, defina un extremo para el servicio de manera imperativa mediante código, de manera declarativa mediante configuración o usando extremos predeterminados y, a continuación, cree una instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="c3ed3-104">Para comenzar a recibir mensajes, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="c3ed3-105">Esto crea y abre el agente de escucha del servicio.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="c3ed3-106">Hospedar un servicio de esta manera se conoce a menudo como "autohospedaje", puesto que la aplicación administrada está haciendo el propio trabajo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="c3ed3-107">Para cerrar el servicio, llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="c3ed3-108">Un servicio también se puede hospedar en un servicio de Windows administrado, en Internet Information Services (IIS) o en Servicio de activación de procesos de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="c3ed3-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="c3ed3-109">opciones para un servicio de hospedaje, vea [servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c3ed3-109"> hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
 <span data-ttu-id="c3ed3-110">Hospedar un servicio en una aplicación administrada es la opción más flexible porque es la que necesita una menor infraestructura para su implementación.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="c3ed3-111">hospedar servicios en las aplicaciones administradas, vea [hospedaje en una aplicación administrada](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="c3ed3-111"> hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="c3ed3-112">El siguiente procedimiento muestra cómo implementar un servicio autohospedado en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>  
  
### <a name="to-create-a-self-hosted-service"></a><span data-ttu-id="c3ed3-113">Creación de un servicio autohospedado</span><span class="sxs-lookup"><span data-stu-id="c3ed3-113">To create a self-hosted service</span></span>  
  
1.  <span data-ttu-id="c3ed3-114">Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y seleccione **New**, **proyecto...**  desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-114">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New**, **Project...** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="c3ed3-115">En el **plantillas instaladas** lista, seleccione **Visual C#**, **Windows** o **Visual Basic**, **Windows**.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-115">In the **Installed Templates** list, select **Visual C#**, **Windows** or **Visual Basic**, **Windows**.</span></span> <span data-ttu-id="c3ed3-116">En función de su [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] configuración, uno o ambos de estos pueden estar bajo el **otros lenguajes** nodo en el **plantillas instaladas** lista.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-116">Depending on your [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] settings, one or both of these may be under the **Other Languages** node in the **Installed Templates** list.</span></span>  
  
3.  <span data-ttu-id="c3ed3-117">Seleccione **aplicación de consola** desde el **Windows** lista.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-117">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="c3ed3-118">Tipo de `SelfHost` en el **nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-118">Type `SelfHost` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="c3ed3-119">Haga clic en **SelfHost** en **el Explorador de soluciones** y seleccione **Agregar referencia...** . Seleccione **System.ServiceModel** desde el **.NET** ficha y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference...**. Select **System.ServiceModel** from the **.NET** tab and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="c3ed3-120">Si el **el Explorador de soluciones** ventana no está visible, seleccione **el Explorador de soluciones** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-120">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="c3ed3-121">Haga doble clic en **Program.cs** o **Module1.vb** en **el Explorador de soluciones** para abrirlo en la ventana de código si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-121">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window if it is not already open.</span></span> <span data-ttu-id="c3ed3-122">Agregue las instrucciones siguientes en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-122">Add the following statements at the top of the file.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]  
  
6.  <span data-ttu-id="c3ed3-123">Defina e implemente un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-123">Define and implement a service contract.</span></span> <span data-ttu-id="c3ed3-124">En este ejemplo se define un `HelloWorldService` que devuelve un mensaje en función de la entrada al servicio.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-124">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]  
  
    > [!NOTE]
    >  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="c3ed3-125">cómo definir e implementar una interfaz de servicio, consulte [Cómo: definir un contrato de servicio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) y [Cómo: implementar un contrato de servicio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="c3ed3-125"> how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>  
  
7.  <span data-ttu-id="c3ed3-126">Al principio del método `Main`, cree una instancia de la clase <xref:System.Uri> con la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-126">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]  
  
8.  <span data-ttu-id="c3ed3-127">Cree una instancia de la clase <xref:System.ServiceModel.ServiceHost>, pasando un <xref:System.Type> que representa el tipo de servicio y el Identificador uniforme de recursos (URI) de la dirección base al <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-127">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="c3ed3-128">Habilite la publicación de metadatos y, a continuación, llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost> para inicializar el servicio y prepararlo para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-128">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]       
  
    > [!NOTE]
    >  <span data-ttu-id="c3ed3-129">En este ejemplo se usan puntos de conexión predeterminados, y este servicio no requiere ningún archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-129">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="c3ed3-130">Si no se configura ningún punto de conexión, el tiempo de ejecución crea uno para cada dirección base de cada contrato de servicio implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-130">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="c3ed3-131">los extremos predeterminados, consulte [configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c3ed3-131"> default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="c3ed3-132">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="to-test-the-service"></a><span data-ttu-id="c3ed3-133">Para probar el servicio</span><span class="sxs-lookup"><span data-stu-id="c3ed3-133">To test the service</span></span>  
  
1.  <span data-ttu-id="c3ed3-134">Presione Ctrl + F5 para ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-134">Press Ctrl + F5 to run the service.</span></span>  
  
2.  <span data-ttu-id="c3ed3-135">Abra **cliente de prueba WCF**.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-135">Open **WCF Test Client**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="c3ed3-136">Para abrir **cliente de prueba WCF**, abra un [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] símbolo y ejecutar **WcfTestClient.exe**.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-136">To open **WCF Test Client**, open a [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] command prompt and execute **WcfTestClient.exe**.</span></span>  
  
3.  <span data-ttu-id="c3ed3-137">Seleccione **Agregar servicio...**  desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-137">Select **Add Service...** from the **File** menu.</span></span>  
  
4.  <span data-ttu-id="c3ed3-138">Tipo de `http://localhost:8080/hello` en el cuadro de dirección y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-138">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="c3ed3-139">Asegúrese de que el servicio se está ejecutando; de lo contrario, este paso producirá un error.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-139">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="c3ed3-140">Si ha cambiado la dirección base en el código, use dicha dirección en este paso.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-140">If you have changed the base address in the code, then use the modified base address in this step.</span></span>  
  
5.  <span data-ttu-id="c3ed3-141">Haga doble clic en **SayHello** en el **Mis proyectos de servicios** nodo.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-141">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="c3ed3-142">Escriba su nombre en el **valor** columna en el **solicitar** lista y haga clic en **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-142">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span> <span data-ttu-id="c3ed3-143">Aparece un mensaje de respuesta en el **respuesta** lista.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-143">A reply message appears in the **Response** list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3ed3-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3ed3-144">Example</span></span>  
 <span data-ttu-id="c3ed3-145">El siguiente ejemplo crea un objeto <xref:System.ServiceModel.ServiceHost> para hospedar un servicio de tipo `HelloWorldService`, y, a continuación, llama al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-145">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="c3ed3-146">Se proporciona una dirección base mediante código, se habilita la publicación de metadatos y se usan puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c3ed3-146">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>  
  
 [!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
 [!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c3ed3-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3ed3-147">See Also</span></span>  
 <xref:System.Uri>  
 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>  
 <xref:System.Configuration.ConfigurationManager>  
 [<span data-ttu-id="c3ed3-148">Cómo: hospedar un servicio WCF en IIS</span><span class="sxs-lookup"><span data-stu-id="c3ed3-148">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
 [<span data-ttu-id="c3ed3-149">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="c3ed3-149">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="c3ed3-150">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c3ed3-150">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="c3ed3-151">Cómo definir un contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="c3ed3-151">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [<span data-ttu-id="c3ed3-152">Cómo implementar un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="c3ed3-152">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="c3ed3-153">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="c3ed3-153">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="c3ed3-154">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c3ed3-154">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="c3ed3-155">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c3ed3-155">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)
