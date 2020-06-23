---
title: 'Tutorial: creación de un cliente de Windows Communication Foundation'
description: Obtenga información sobre cómo crear un cliente mediante la recuperación de metadatos desde un servicio WCF como parte de una serie de artículos que le ayudarán a empezar a crear una aplicación WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: d5a2a2b5175c9e34eaf1dbaff20ac57f34117c4e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246329"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="af378-103">Tutorial: creación de un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="af378-103">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="af378-104">En este tutorial se describe el cuarto de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="af378-104">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="af378-105">Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="af378-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="af378-106">La siguiente tarea para crear una aplicación WCF es crear un cliente mediante la recuperación de los metadatos de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="af378-106">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="af378-107">Use Visual Studio para agregar una referencia de servicio, que obtiene los metadatos del punto de conexión MEX del servicio.</span><span class="sxs-lookup"><span data-stu-id="af378-107">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="af378-108">A continuación, Visual Studio genera un archivo de código fuente administrado para un proxy de cliente en el idioma elegido.</span><span class="sxs-lookup"><span data-stu-id="af378-108">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="af378-109">También crea un archivo de configuración de cliente (*App.config*).</span><span class="sxs-lookup"><span data-stu-id="af378-109">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="af378-110">Este archivo permite a la aplicación cliente conectarse al servicio en un extremo.</span><span class="sxs-lookup"><span data-stu-id="af378-110">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="af378-111">Si llama a un servicio WCF desde un proyecto de biblioteca de clases en Visual Studio, use la característica **Agregar referencia de servicio** para generar automáticamente un proxy y el archivo de configuración asociado.</span><span class="sxs-lookup"><span data-stu-id="af378-111">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="af378-112">Sin embargo, dado que los proyectos de biblioteca de clases no usan este archivo de configuración, debe agregar la configuración del archivo de configuración generado al archivo *App.config* para el ejecutable que llama a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="af378-112">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="af378-113">Como alternativa, use la [herramienta de utilidad de metadatos de ServiceModel](#servicemodel-metadata-utility-tool) en lugar de Visual Studio para generar la clase de proxy y el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="af378-113">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="af378-114">La aplicación cliente usa la clase de proxy generada para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="af378-114">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="af378-115">Este procedimiento se describe en [Tutorial: usar un cliente](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="af378-115">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="af378-116">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="af378-116">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="af378-117">Cree y configure un proyecto de aplicación de consola para el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="af378-117">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="af378-118">Agregue una referencia de servicio al servicio WCF para generar la clase de proxy y los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="af378-118">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="af378-119">Creación de un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="af378-119">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="af378-120">Cree un proyecto de aplicación de consola en Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="af378-120">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="af378-121">En el menú **archivo** , seleccione **abrir**  >  **proyecto o solución** y busque la solución **gettingstarted** que creó anteriormente (*gettingstarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="af378-121">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="af378-122">seleccione **Open**(Abrir).</span><span class="sxs-lookup"><span data-stu-id="af378-122">Select **Open**.</span></span>

    2. <span data-ttu-id="af378-123">En el menú **Ver** , seleccione **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="af378-123">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="af378-124">En la ventana **Explorador de soluciones** , seleccione la solución **gettingstarted** (nodo superior) y, a continuación, seleccione **Agregar**  >  **nuevo proyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="af378-124">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="af378-125">En la ventana **Agregar nuevo proyecto** , en el lado izquierdo, seleccione la categoría **escritorio de Windows** en **Visual C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="af378-125">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="af378-126">Seleccione la plantilla **aplicación de consola (.NET Framework)** y escriba *GettingStartedClient* para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="af378-126">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="af378-127">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="af378-127">Select **OK**.</span></span>

2. <span data-ttu-id="af378-128">Agregue una referencia en el proyecto **GettingStartedClient** al <xref:System.ServiceModel> ensamblado:</span><span class="sxs-lookup"><span data-stu-id="af378-128">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="af378-129">En la ventana **Explorador de soluciones** , seleccione la carpeta **referencias** en el proyecto **GettingStartedClient** y, a continuación, seleccione **Agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="af378-129">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="af378-130">En la ventana **Agregar referencia** , en **ensamblados** en el lado izquierdo de la ventana, seleccione **marco de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="af378-130">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="af378-131">Busque y seleccione **System. ServiceModel**y, después, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="af378-131">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="af378-132">Guarde la solución seleccionando **archivo**  >  **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="af378-132">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="af378-133">Agregue una referencia de servicio al servicio de calculadora:</span><span class="sxs-lookup"><span data-stu-id="af378-133">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="af378-134">En la ventana **Explorador de soluciones** , seleccione la carpeta **referencias** en el proyecto **GettingStartedClient** y, a continuación, seleccione **Agregar referencia de servicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="af378-134">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="af378-135">En la ventana **Agregar referencia de servicio** , seleccione **detectar**.</span><span class="sxs-lookup"><span data-stu-id="af378-135">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="af378-136">El servicio CalculatorService se inicia y Visual Studio lo muestra en el cuadro **servicios** .</span><span class="sxs-lookup"><span data-stu-id="af378-136">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="af378-137">Seleccione **CalculatorService** para expandirlo y mostrar los contratos de servicio implementados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="af378-137">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="af378-138">Deje el **espacio de nombres** predeterminado y elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="af378-138">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="af378-139">Visual Studio agrega un nuevo elemento en la carpeta **servicios conectados** del proyecto **GettingStartedClient** .</span><span class="sxs-lookup"><span data-stu-id="af378-139">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="af378-140">Herramienta de utilidad de metadatos de ServiceModel</span><span class="sxs-lookup"><span data-stu-id="af378-140">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="af378-141">En los siguientes ejemplos se muestra cómo usar opcionalmente la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el archivo de clase de proxy.</span><span class="sxs-lookup"><span data-stu-id="af378-141">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="af378-142">Esta herramienta genera el archivo de clase de proxy y el archivo de *App.config* .</span><span class="sxs-lookup"><span data-stu-id="af378-142">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="af378-143">En los siguientes ejemplos se muestra cómo generar el proxy en C# y Visual Basic, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="af378-143">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="af378-144">Archivo de configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="af378-144">Client configuration file</span></span>

<span data-ttu-id="af378-145">Después de crear el cliente, Visual Studio crea el archivo de configuración de **App.config** en el proyecto **GettingStartedClient** , que debe ser similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af378-145">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="af378-146">En la [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) sección, observe el [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="af378-146">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="af378-147">El elemento de \*\* &lt; punto de conexión &gt; \*\* define el extremo que el cliente usa para tener acceso al servicio de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="af378-147">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="af378-148">Dirección: `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="af378-148">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="af378-149">Dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="af378-149">The address of the endpoint.</span></span>
- <span data-ttu-id="af378-150">Contrato de servicio: `ServiceReference1.ICalculator` .</span><span class="sxs-lookup"><span data-stu-id="af378-150">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="af378-151">El contrato de servicio controla la comunicación entre el cliente de WCF y el servicio.</span><span class="sxs-lookup"><span data-stu-id="af378-151">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="af378-152">Visual Studio generó este contrato cuando se usaba su **Agregar referencia de servicio** función.</span><span class="sxs-lookup"><span data-stu-id="af378-152">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="af378-153">Básicamente es una copia del contrato que definió en el proyecto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="af378-153">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="af378-154">Enlace: <xref:System.ServiceModel.WSHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="af378-154">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="af378-155">El enlace especifica HTTP como el transporte, la seguridad interoperable y otros detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="af378-155">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="af378-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="af378-156">Next steps</span></span>

<span data-ttu-id="af378-157">En este tutorial, ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="af378-157">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="af378-158">Cree y configure un proyecto de aplicación de consola para el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="af378-158">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="af378-159">Agregue una referencia de servicio al servicio WCF para generar la clase de proxy y los archivos de configuración para la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="af378-159">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="af378-160">Avance al siguiente tutorial para aprender a usar el cliente generado.</span><span class="sxs-lookup"><span data-stu-id="af378-160">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="af378-161">Tutorial: uso de un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="af378-161">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
