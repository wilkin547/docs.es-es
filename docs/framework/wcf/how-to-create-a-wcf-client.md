---
title: 'Tutorial: Crear un cliente de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184109"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="4787f-102">Tutorial: Crear un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="4787f-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="4787f-103">En este tutorial se describe la cuarta de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4787f-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="4787f-104">Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a](getting-started-tutorial.md)las aplicaciones de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="4787f-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="4787f-105">La siguiente tarea para crear una aplicación WCF es crear un cliente mediante la recuperación de metadatos de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="4787f-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="4787f-106">Use Visual Studio para agregar una referencia de servicio, que obtiene los metadatos del extremo MEX del servicio.</span><span class="sxs-lookup"><span data-stu-id="4787f-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="4787f-107">A continuación, Visual Studio genera un archivo de código fuente administrado para un proxy de cliente en el idioma que ha elegido.</span><span class="sxs-lookup"><span data-stu-id="4787f-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="4787f-108">También crea un archivo de configuración de cliente (*App.config*).</span><span class="sxs-lookup"><span data-stu-id="4787f-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="4787f-109">Este archivo permite a la aplicación cliente conectarse al servicio en un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="4787f-109">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="4787f-110">Si llama a un servicio WCF desde un proyecto de biblioteca de clases en Visual Studio, use la característica **Agregar referencia** de servicio para generar automáticamente un proxy y un archivo de configuración asociado.</span><span class="sxs-lookup"><span data-stu-id="4787f-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="4787f-111">Sin embargo, dado que los proyectos de biblioteca de clases no usan este archivo de configuración, debe agregar la configuración del archivo de configuración generado al archivo *App.config* para el ejecutable que llama a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="4787f-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="4787f-112">Como alternativa, use la herramienta Utilidad de metadatos de [ServiceModel](#servicemodel-metadata-utility-tool) en lugar de Visual Studio para generar la clase de proxy y el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4787f-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="4787f-113">La aplicación cliente usa la clase de proxy generada para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="4787f-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="4787f-114">Este procedimiento se describe en [Tutorial: Usar un cliente](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="4787f-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="4787f-115">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="4787f-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="4787f-116">Crear y configurar un proyecto de aplicación de consola para el cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="4787f-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="4787f-117">Agregue una referencia de servicio al servicio WCF para generar la clase de proxy y los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="4787f-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="4787f-118">Crear un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="4787f-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="4787f-119">Cree un proyecto de aplicación de consola en Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="4787f-119">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="4787f-120">En el menú **Archivo,** seleccione **Abrir** > **proyecto/solución** y vaya a la solución **GettingStarted** que creó anteriormente (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="4787f-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="4787f-121">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4787f-121">Select **Open**.</span></span>

    2. <span data-ttu-id="4787f-122">En el menú **Ver** , seleccione **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="4787f-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="4787f-123">En la ventana **Explorador** de soluciones, seleccione la solución **GettingStarted** (nodo superior) y, a continuación, seleccione **Agregar** > **nuevo proyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="4787f-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="4787f-124">En la ventana **Agregar nuevo proyecto,** en el lado izquierdo, seleccione la categoría Escritorio de **Windows** en **Visual C** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="4787f-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="4787f-125">Seleccione la plantilla Aplicación de **consola (.NET Framework)** y escriba *GettingStartedClient* para **El nombre**.</span><span class="sxs-lookup"><span data-stu-id="4787f-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="4787f-126">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4787f-126">Select **OK**.</span></span>

2. <span data-ttu-id="4787f-127">Agregue una referencia en el proyecto <xref:System.ServiceModel> **GettingStartedClient** al ensamblado:</span><span class="sxs-lookup"><span data-stu-id="4787f-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="4787f-128">En el **Explorador** de soluciones ventana, seleccione el **referencias** carpeta en el **GettingStartedClient** proyecto y, a continuación, seleccione **agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="4787f-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="4787f-129">En la ventana **Agregar referencia,** en **Ensamblados** en el lado izquierdo de la ventana, seleccione **Framework**.</span><span class="sxs-lookup"><span data-stu-id="4787f-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="4787f-130">Busque y seleccione **System.ServiceModel**y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4787f-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="4787f-131">Guarde la solución seleccionando **Guardar archivo** > **todo**.</span><span class="sxs-lookup"><span data-stu-id="4787f-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="4787f-132">Agregue una referencia de servicio al servicio de calculadora:</span><span class="sxs-lookup"><span data-stu-id="4787f-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="4787f-133">En el **Explorador** de soluciones ventana, seleccione el **referencias** carpeta en el **GettingStartedClient** proyecto y, a continuación, seleccione **agregar referencia** de servicio en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="4787f-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="4787f-134">En la ventana **Agregar referencia de servicio,** seleccione **Detectar**.</span><span class="sxs-lookup"><span data-stu-id="4787f-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="4787f-135">El servicio CalculatorService se inicia y Visual Studio lo muestra en el cuadro **Servicios.**</span><span class="sxs-lookup"><span data-stu-id="4787f-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="4787f-136">Seleccione **CalculatorService** para expandirlo y mostrar los contratos de servicio implementados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="4787f-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="4787f-137">Deje el **espacio de nombres** predeterminado y elija **Ok**.</span><span class="sxs-lookup"><span data-stu-id="4787f-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="4787f-138">Visual Studio agrega un nuevo elemento en la carpeta **Servicios conectados** en el **GettingStartedClient** proyecto.</span><span class="sxs-lookup"><span data-stu-id="4787f-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="4787f-139">Herramienta de utilidad de metadatos de ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4787f-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="4787f-140">En los ejemplos siguientes se muestra cómo usar opcionalmente la herramienta Delación de metadatos de [ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el archivo de clase de proxy.</span><span class="sxs-lookup"><span data-stu-id="4787f-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="4787f-141">Esta herramienta genera el archivo de clase de proxy y el archivo *App.config.*</span><span class="sxs-lookup"><span data-stu-id="4787f-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="4787f-142">En los ejemplos siguientes se muestra cómo generar el proxy en C- y Visual Basic, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="4787f-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="4787f-143">Archivo de configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="4787f-143">Client configuration file</span></span>

<span data-ttu-id="4787f-144">Después de crear el cliente, Visual Studio crea el archivo de configuración **App.config** en el proyecto **GettingStartedClient,** que debe ser similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4787f-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="4787f-145">En la [ \<](../configure-apps/file-schema/wcf/endpoint-element.md) [ \<sección system.serviceModel>,](../configure-apps/file-schema/wcf/system-servicemodel.md) observe el extremo>elemento.</span><span class="sxs-lookup"><span data-stu-id="4787f-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="4787f-146">El elemento \*\* &lt;endpoint&gt; \*\* define el punto de conexión que el cliente utiliza para tener acceso al servicio de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4787f-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="4787f-147">Dirección: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="4787f-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="4787f-148">Dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="4787f-148">The address of the endpoint.</span></span>
- <span data-ttu-id="4787f-149">Contrato de `ServiceReference1.ICalculator`servicio: .</span><span class="sxs-lookup"><span data-stu-id="4787f-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="4787f-150">El contrato de servicio controla la comunicación entre el cliente WCF y el servicio.</span><span class="sxs-lookup"><span data-stu-id="4787f-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="4787f-151">Visual Studio generó este contrato cuando usó su **función Agregar referencia** de servicio.</span><span class="sxs-lookup"><span data-stu-id="4787f-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="4787f-152">Es esencialmente una copia del contrato que definió en el gettingStartedLib proyecto.</span><span class="sxs-lookup"><span data-stu-id="4787f-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="4787f-153">Encuadernación: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="4787f-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="4787f-154">El enlace especifica HTTP como el transporte, la seguridad interoperable y otros detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="4787f-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4787f-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4787f-155">Next steps</span></span>

<span data-ttu-id="4787f-156">En este tutorial, ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="4787f-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="4787f-157">Crear y configurar un proyecto de aplicación de consola para el cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="4787f-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="4787f-158">Agregue una referencia de servicio al servicio WCF para generar la clase de proxy y los archivos de configuración para la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="4787f-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="4787f-159">Vaya al siguiente tutorial para aprender a usar el cliente generado.</span><span class="sxs-lookup"><span data-stu-id="4787f-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4787f-160">Tutorial: Usar un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="4787f-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
