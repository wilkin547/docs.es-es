---
title: 'Tutorial: Crear a un cliente de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: a16a0ccabfd0f9fbe69db1ea88d4613185f3c1da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174374"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="08634-102">Tutorial: Crear a un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="08634-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="08634-103">Este tutorial describe la cuarta de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="08634-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="08634-104">Para obtener información general de los tutoriales, consulte [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="08634-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="08634-105">La siguiente tarea para crear una aplicación de WCF es crear a un cliente mediante la recuperación de metadatos de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="08634-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="08634-106">Usar Visual Studio para agregar una referencia de servicio, que obtiene los metadatos del punto de conexión MEX del servicio.</span><span class="sxs-lookup"><span data-stu-id="08634-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="08634-107">Visual Studio, a continuación, genera un archivo de código fuente administrado para un proxy de cliente en el idioma que haya elegido.</span><span class="sxs-lookup"><span data-stu-id="08634-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="08634-108">También crea un archivo de configuración de cliente (*App.config*).</span><span class="sxs-lookup"><span data-stu-id="08634-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="08634-109">Este archivo permite que la aplicación cliente para conectarse al servicio en un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="08634-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="08634-110">Si se llama a un servicio WCF desde un proyecto de biblioteca de clases en Visual Studio, utilice el **Add Service Reference** característica para generar automáticamente un proxy y el archivo de configuración asociada.</span><span class="sxs-lookup"><span data-stu-id="08634-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="08634-111">Sin embargo, dado que los proyectos de biblioteca de clases no usan este archivo de configuración, deberá agregar la configuración en el archivo de configuración generado para el *App.config* archivo para el archivo ejecutable que llama a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="08634-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="08634-112">Como alternativa, use el [herramienta de utilidad de metadatos de ServiceModel](#servicemodel-metadata-utility-tool) en lugar de Visual Studio para generar el archivo de clase y la configuración de proxy.</span><span class="sxs-lookup"><span data-stu-id="08634-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="08634-113">La aplicación cliente usa la clase de proxy generada para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="08634-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="08634-114">Este procedimiento se describe en [Tutorial: Usar un cliente](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="08634-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="08634-115">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="08634-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="08634-116">Crear y configurar un proyecto de aplicación de consola para el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="08634-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="08634-117">Agregue una referencia de servicio al servicio WCF para generar los archivos de clase y la configuración de proxy.</span><span class="sxs-lookup"><span data-stu-id="08634-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="08634-118">Crear a un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="08634-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="08634-119">Cree un proyecto de aplicación de consola en Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="08634-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="08634-120">Desde el **archivo** menú, seleccione **abierto** > **proyecto/solución** y vaya a la **GettingStarted** solución ha creado anteriormente (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="08634-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="08634-121">Seleccione **abierto**.</span><span class="sxs-lookup"><span data-stu-id="08634-121">Select **Open**.</span></span>

    2. <span data-ttu-id="08634-122">Desde el **vista** menú, seleccione **el Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="08634-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="08634-123">En el **el Explorador de soluciones** ventana, seleccione el **GettingStarted** (nodo superior) de la solución y, a continuación, seleccione **agregar** > **denuevoproyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="08634-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="08634-124">En el **Agregar nuevo proyecto** ventana, en el lado izquierdo, seleccione el **Windows Desktop** categoría **Visual C#**  o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="08634-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="08634-125">Seleccione el **aplicación de consola (.NET Framework)** plantilla y escriba *GettingStartedClient* para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="08634-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="08634-126">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08634-126">Select **OK**.</span></span>

2. <span data-ttu-id="08634-127">Agregue una referencia en el **GettingStartedClient** proyecto a la <xref:System.ServiceModel> ensamblado:</span><span class="sxs-lookup"><span data-stu-id="08634-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1.  <span data-ttu-id="08634-128">En el **el Explorador de soluciones** ventana, seleccione el **referencias** carpeta bajo la **GettingStartedClient** proyecto y, a continuación, seleccione **Agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="08634-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="08634-129">En el **Agregar referencia** ventana, en **ensamblados** en el lado izquierdo de la ventana, seleccione **Framework**.</span><span class="sxs-lookup"><span data-stu-id="08634-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="08634-130">Busque y seleccione **System.ServiceModel**y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08634-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="08634-131">Guarde la solución seleccionando **archivo** > **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="08634-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="08634-132">Agregue una referencia de servicio al servicio de calculadora:</span><span class="sxs-lookup"><span data-stu-id="08634-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="08634-133">En el **el Explorador de soluciones** ventana, seleccione el **referencias** carpeta bajo la **GettingStartedClient** proyecto y, a continuación, seleccione **Add Service Reference**  en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="08634-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="08634-134">En el **Add Service Reference** ventana, seleccione **Discover**.</span><span class="sxs-lookup"><span data-stu-id="08634-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="08634-135">El servicio se inicia CalculatorService y Visual Studio lo muestra en el **servicios** cuadro.</span><span class="sxs-lookup"><span data-stu-id="08634-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="08634-136">Seleccione **CalculatorService** para expandirlo y mostrar los contratos de servicio implementados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="08634-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="08634-137">Deje el valor predeterminado **Namespace** y elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08634-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="08634-138">Visual Studio agrega un elemento nuevo bajo el **Connected Services** carpeta en el **GettingStartedClient** proyecto.</span><span class="sxs-lookup"><span data-stu-id="08634-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="08634-139">Herramienta de utilidad de metadatos de ServiceModel</span><span class="sxs-lookup"><span data-stu-id="08634-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="08634-140">Los ejemplos siguientes muestran cómo utilizar opcionalmente la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el archivo de clase de proxy.</span><span class="sxs-lookup"><span data-stu-id="08634-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="08634-141">Esta herramienta genera el archivo de clase de proxy y el *App.config* archivo.</span><span class="sxs-lookup"><span data-stu-id="08634-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="08634-142">Los ejemplos siguientes muestran cómo generar el proxy en C# y Visual Basic, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="08634-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="08634-143">Archivo de configuración de cliente</span><span class="sxs-lookup"><span data-stu-id="08634-143">Client configuration file</span></span>

<span data-ttu-id="08634-144">Después de crear el cliente, Visual Studio crea el **App.config** archivo de configuración en el **GettingStartedClient** proyecto, que debe ser similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08634-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

<span data-ttu-id="08634-145">En el [ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) sección, tenga en cuenta la [ \<punto de conexión >](../configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="08634-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="08634-146">El **&lt;extremo&gt;** elemento define el punto de conexión que el cliente utiliza para tener acceso al servicio como sigue:</span><span class="sxs-lookup"><span data-stu-id="08634-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>
- <span data-ttu-id="08634-147">Dirección: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="08634-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="08634-148">Dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="08634-148">The address of the endpoint.</span></span>
- <span data-ttu-id="08634-149">Contrato de servicio: `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="08634-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="08634-150">El contrato de servicio controla la comunicación entre el cliente de WCF y el servicio.</span><span class="sxs-lookup"><span data-stu-id="08634-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="08634-151">Este contrato generada por Visual Studio cuando usó su **Add Service Reference** función.</span><span class="sxs-lookup"><span data-stu-id="08634-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="08634-152">Es básicamente una copia del contrato que define en el proyecto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="08634-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="08634-153">Enlace: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="08634-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="08634-154">El enlace especifica HTTP como transporte, seguridad interoperable y otros detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="08634-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="08634-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="08634-155">Next steps</span></span>

<span data-ttu-id="08634-156">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="08634-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="08634-157">Crear y configurar un proyecto de aplicación de consola para el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="08634-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="08634-158">Agregue una referencia de servicio al servicio WCF para generar los archivos de clase y la configuración de proxy para la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="08634-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="08634-159">En el siguiente tutorial para aprender a usar al cliente generado.</span><span class="sxs-lookup"><span data-stu-id="08634-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="08634-160">Tutorial: Usar a un cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="08634-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
