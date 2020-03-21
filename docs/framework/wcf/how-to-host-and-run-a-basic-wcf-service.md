---
title: 'Tutorial: Hospedar y ejecutar un servicio básico de Windows Communication Foundation'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184080"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="402ab-102">Tutorial: Hospedar y ejecutar un servicio básico de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="402ab-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="402ab-103">En este tutorial se describe la tercera de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="402ab-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="402ab-104">Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a](getting-started-tutorial.md)las aplicaciones de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="402ab-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="402ab-105">La siguiente tarea para crear una aplicación WCF es hospedar un servicio WCF en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="402ab-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="402ab-106">Un servicio WCF expone uno o varios *extremos,* cada uno de los cuales expone una o varias operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="402ab-107">Un punto de conexión de servicio especifica la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="402ab-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="402ab-108">Una dirección donde se puede encontrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-108">An address where you can find the service.</span></span>
- <span data-ttu-id="402ab-109">Un enlace que contiene la información que describe cómo un cliente debe comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-109">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="402ab-110">Un contrato que define la funcionalidad que el servicio proporciona a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="402ab-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="402ab-111">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="402ab-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="402ab-112">Crear y configurar un proyecto de aplicación de consola para hospedar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="402ab-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="402ab-113">Agregue código para hospedar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="402ab-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="402ab-114">Actualice el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="402ab-114">Update the configuration file.</span></span>
> - <span data-ttu-id="402ab-115">Inicie el servicio WCF y compruebe que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="402ab-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="402ab-116">Crear y configurar un proyecto de aplicación de consola para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="402ab-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="402ab-117">Cree un proyecto de aplicación de consola en Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="402ab-117">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="402ab-118">En el menú **Archivo,** seleccione **Abrir** > **proyecto/solución** y vaya a la solución **GettingStarted** que creó anteriormente (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="402ab-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="402ab-119">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="402ab-119">Select **Open**.</span></span>

    2. <span data-ttu-id="402ab-120">En el menú **Ver** , seleccione **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="402ab-120">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="402ab-121">En la ventana **Explorador** de soluciones, seleccione la solución **GettingStarted** (nodo superior) y, a continuación, seleccione **Agregar** > **nuevo proyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="402ab-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="402ab-122">En la ventana **Agregar nuevo proyecto,** en el lado izquierdo, seleccione la categoría Escritorio de **Windows** en **Visual C** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="402ab-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="402ab-123">Seleccione la plantilla Aplicación de **consola (.NET Framework)** y escriba *GettingStartedHost* para **el nombre**.</span><span class="sxs-lookup"><span data-stu-id="402ab-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="402ab-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="402ab-124">Select **OK**.</span></span>

2. <span data-ttu-id="402ab-125">Agregue una referencia en el proyecto **GettingStartedHost** al proyecto **GettingStartedLib:**</span><span class="sxs-lookup"><span data-stu-id="402ab-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="402ab-126">En la ventana **Explorador** de soluciones, seleccione la carpeta **Referencias** en el proyecto **GettingStartedHost** y, a continuación, seleccione **Agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="402ab-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="402ab-127">En el cuadro de diálogo **Agregar referencia,** en **Proyectos** en el lado izquierdo de la ventana, seleccione **Solución**.</span><span class="sxs-lookup"><span data-stu-id="402ab-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="402ab-128">Seleccione **GettingStartedLib** en la sección central de la ventana y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="402ab-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="402ab-129">Esta acción hace que los tipos definidos en el **GettingStartedLib** proyecto disponible para el **GettingStartedHost** proyecto.</span><span class="sxs-lookup"><span data-stu-id="402ab-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="402ab-130">Agregue una referencia en el proyecto <xref:System.ServiceModel> **GettingStartedHost** al ensamblado:</span><span class="sxs-lookup"><span data-stu-id="402ab-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="402ab-131">En la ventana **Explorador** de soluciones, seleccione la carpeta **Referencias** en el proyecto **GettingStartedHost** y, a continuación, seleccione **Agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="402ab-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="402ab-132">En la ventana **Agregar referencia,** en **Ensamblados** en el lado izquierdo de la ventana, seleccione **Framework**.</span><span class="sxs-lookup"><span data-stu-id="402ab-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="402ab-133">Seleccione **System.ServiceModel**y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="402ab-133">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="402ab-134">Guarde la solución seleccionando **Guardar archivo** > **todo**.</span><span class="sxs-lookup"><span data-stu-id="402ab-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="402ab-135">Agregar código para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="402ab-135">Add code to host the service</span></span>

<span data-ttu-id="402ab-136">Para hospedar el servicio, agregue código para realizar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="402ab-136">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="402ab-137">Cree un URI para la dirección base.</span><span class="sxs-lookup"><span data-stu-id="402ab-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="402ab-138">Cree una instancia de clase para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="402ab-139">Cree un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="402ab-140">Habilitar el intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="402ab-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="402ab-141">Abra el host de servicio para escuchar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="402ab-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="402ab-142">Realice los siguientes cambios en el código:</span><span class="sxs-lookup"><span data-stu-id="402ab-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="402ab-143">Abra el **archivo Program.cs** o **Module1.vb** en el proyecto **GettingStartedHost** y reemplace su código por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="402ab-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb)    ;

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```

    <span data-ttu-id="402ab-144">Para obtener información sobre cómo funciona este código, consulte [Pasos](#service-hosting-program-steps)del programa de hospedaje de servicios.</span><span class="sxs-lookup"><span data-stu-id="402ab-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="402ab-145">Actualice las propiedades del proyecto:</span><span class="sxs-lookup"><span data-stu-id="402ab-145">Update the project properties:</span></span>

   1. <span data-ttu-id="402ab-146">En la ventana Explorador de **soluciones,** seleccione la carpeta **GettingStartedHost** y, a continuación, seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="402ab-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="402ab-147">En la página de propiedades **GettingStartedHost,** seleccione la pestaña **Aplicación:**</span><span class="sxs-lookup"><span data-stu-id="402ab-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="402ab-148">En el caso de los proyectos de C, seleccione **GettingStartedHost.Program** en la lista **de objetos** de inicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="402ab-149">Para proyectos de Visual Basic, seleccione **Service.Program** en la lista Objetos de **inicio.**</span><span class="sxs-lookup"><span data-stu-id="402ab-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="402ab-150">En el menú **Archivo,** seleccione **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="402ab-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="402ab-151">Verifique que el servicio esté funcionando</span><span class="sxs-lookup"><span data-stu-id="402ab-151">Verify the service is working</span></span>

1. <span data-ttu-id="402ab-152">Compile la solución y, a continuación, ejecute la aplicación de consola **GettingStartedHost** desde dentro de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="402ab-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="402ab-153">El servicio debe ejecutarse con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="402ab-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="402ab-154">Dado que abrió Visual Studio con privilegios de administrador, al ejecutar **GettingStartedHost** en Visual Studio, la aplicación también se ejecuta con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="402ab-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="402ab-155">Como alternativa, puede abrir un nuevo símbolo del sistema como administrador (seleccione **Más** > **ejecución como administrador** en el menú contextual) y ejecutar **GettingStartedHost.exe** dentro de él.</span><span class="sxs-lookup"><span data-stu-id="402ab-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="402ab-156">Abra un navegador web y vaya a `http://localhost:8000/GettingStarted/CalculatorService`la página del servicio en .</span><span class="sxs-lookup"><span data-stu-id="402ab-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="402ab-157">Servicios como este requieren el permiso adecuado para registrar direcciones HTTP en el equipo para escucharlas.</span><span class="sxs-lookup"><span data-stu-id="402ab-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="402ab-158">Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP.</span><span class="sxs-lookup"><span data-stu-id="402ab-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="402ab-159">Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="402ab-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="402ab-160">Pasos del programa de alojamiento de servicios</span><span class="sxs-lookup"><span data-stu-id="402ab-160">Service hosting program steps</span></span>

<span data-ttu-id="402ab-161">Los pasos del código que agregó para hospedar el servicio se describen de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="402ab-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="402ab-162">**Paso 1:** Cree una `Uri` instancia de la clase para contener la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="402ab-163">Una dirección URL que contiene una dirección base tiene un URI opcional que identifica un servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="402ab-164">La dirección base tiene el `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`siguiente formato: .</span><span class="sxs-lookup"><span data-stu-id="402ab-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="402ab-165">La dirección base del servicio de calculadora utiliza el transporte HTTP, localhost, puerto 8000 y el segmento URI, GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="402ab-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="402ab-166">**Paso 2:** Cree una <xref:System.ServiceModel.ServiceHost> instancia de la clase, que se utiliza para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="402ab-167">El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="402ab-168">**Paso 3**: <xref:System.ServiceModel.Description.ServiceEndpoint> Crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="402ab-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="402ab-169">Un extremo de servicio consta de una dirección, un enlace y un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="402ab-170">El <xref:System.ServiceModel.Description.ServiceEndpoint> constructor se compone del tipo de interfaz de contrato de servicio, un enlace y una dirección.</span><span class="sxs-lookup"><span data-stu-id="402ab-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="402ab-171">El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="402ab-172">El enlace para <xref:System.ServiceModel.WSHttpBinding>este ejemplo es , que es un enlace integrado y se conecta a los extremos que se ajustan a las especificaciones WS-\*.</span><span class="sxs-lookup"><span data-stu-id="402ab-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="402ab-173">Para obtener más información acerca de los enlaces WCF, vea [información general sobre enlaces WCF](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="402ab-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="402ab-174">Anexe la dirección a la dirección base para identificar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="402ab-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="402ab-175">El código especifica la dirección como CalculatorService y la `http://localhost:8000/GettingStarted/CalculatorService`dirección completa para el punto de conexión como .</span><span class="sxs-lookup"><span data-stu-id="402ab-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="402ab-176">Para .NET Framework versión 4 y versiones posteriores, agregar un punto de conexión de servicio es opcional.</span><span class="sxs-lookup"><span data-stu-id="402ab-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="402ab-177">Para estas versiones, si no agrega el código o la configuración, WCF agrega un extremo predeterminado para cada combinación de dirección base y contrato implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="402ab-178">Para obtener más información acerca de los puntos de conexión predeterminados, consulte [Especificación de una dirección](specifying-an-endpoint-address.md)de punto de conexión .</span><span class="sxs-lookup"><span data-stu-id="402ab-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="402ab-179">Para obtener más información acerca de los extremos, enlaces y comportamientos predeterminados, vea [Configuración simplificada](simplified-configuration.md) y [Configuración simplificada para servicios WCF.](samples/simplified-configuration-for-wcf-services.md)</span><span class="sxs-lookup"><span data-stu-id="402ab-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="402ab-180">**Paso 4**: Habilitar el intercambio de metadatos.</span><span class="sxs-lookup"><span data-stu-id="402ab-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="402ab-181">Los clientes usan el intercambio de metadatos para generar servidores proxy para llamar a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="402ab-182">Para habilitar el intercambio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> de metadatos, `true`cree una `ServiceMetadataBehavior` instancia, <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> establezca su <xref:System.ServiceModel.ServiceHost> <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> propiedad en y agregue el objeto a la colección de la instancia.</span><span class="sxs-lookup"><span data-stu-id="402ab-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="402ab-183">**Paso 5** <xref:System.ServiceModel.ServiceHost> : Abrir para escuchar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="402ab-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="402ab-184">La aplicación espera a que pulse **Intro**.</span><span class="sxs-lookup"><span data-stu-id="402ab-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="402ab-185">Después de <xref:System.ServiceModel.ServiceHost>que la aplicación crea una instancia, ejecuta un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="402ab-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="402ab-186">Para obtener más información acerca de <xref:System.ServiceModel.ServiceHost>cómo detectar de forma segura las excepciones producidas por , vea [usar cerrar y anular para liberar recursos](samples/use-close-abort-release-wcf-client-resources.md)de cliente WCF .</span><span class="sxs-lookup"><span data-stu-id="402ab-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="402ab-187">Al agregar una biblioteca de servicios WCF, Visual Studio la hospeda automáticamente si la depura inicia iniciando un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="402ab-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="402ab-188">Para evitar conflictos, puede evitar que Visual Studio hosmeque la biblioteca de servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="402ab-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="402ab-189">Seleccione el **GettingStartedLib** proyecto en **el Explorador** de soluciones y elija **propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="402ab-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="402ab-190">Seleccione **Opciones de WCF** y desactive Iniciar host de servicio WCF al depurar otro proyecto en la misma **solución.**</span><span class="sxs-lookup"><span data-stu-id="402ab-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="402ab-191">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="402ab-191">Next steps</span></span>

<span data-ttu-id="402ab-192">En este tutorial, ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="402ab-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="402ab-193">Crear y configurar un proyecto de aplicación de consola para hospedar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="402ab-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="402ab-194">Agregue código para hospedar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="402ab-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="402ab-195">Actualice el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="402ab-195">Update the configuration file.</span></span>
> - <span data-ttu-id="402ab-196">Inicie el servicio WCF y compruebe que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="402ab-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="402ab-197">Avance al siguiente tutorial para aprender a crear un cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="402ab-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="402ab-198">Tutorial: Crear un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="402ab-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
