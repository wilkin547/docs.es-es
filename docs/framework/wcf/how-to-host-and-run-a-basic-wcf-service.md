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
ms.openlocfilehash: ad9536b1f27ba3945bf76d0474de4825033a1e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929108"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="c559e-102">Tutorial: Hospedar y ejecutar un servicio básico de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="c559e-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="c559e-103">Este tutorial describen lo tercio de cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c559e-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="c559e-104">Para obtener información general de los tutoriales, consulte [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="c559e-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="c559e-105">La siguiente tarea para crear una aplicación de WCF que se va a hospedar un servicio WCF en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="c559e-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="c559e-106">Un servicio WCF que expone uno o varios *extremos*, cada uno de los cuales expone una o varias operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="c559e-107">Un extremo de servicio especifica la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="c559e-107">A service endpoint specifies the following information:</span></span> 
- <span data-ttu-id="c559e-108">Una dirección donde se encuentra el servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-108">An address where you can find the service.</span></span>
- <span data-ttu-id="c559e-109">Un enlace que contiene la información que describe cómo un cliente debe comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-109">A binding that contains the information that describes how a client must communicate with the service.</span></span> 
- <span data-ttu-id="c559e-110">Un contrato que define la funcionalidad que proporciona el servicio a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="c559e-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="c559e-111">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="c559e-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="c559e-112">Crear y configurar un proyecto de aplicación de consola para hospedar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c559e-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="c559e-113">Agregue código para hospedar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c559e-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="c559e-114">Actualice el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c559e-114">Update the configuration file.</span></span>
> - <span data-ttu-id="c559e-115">Inicie el servicio WCF y compruebe se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c559e-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="c559e-116">Crear y configurar un proyecto de aplicación de consola para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="c559e-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="c559e-117">Cree un proyecto de aplicación de consola en Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="c559e-117">Create a console app project in Visual Studio:</span></span> 
 
    1. <span data-ttu-id="c559e-118">Desde el **archivo** menú, seleccione **abierto** > **proyecto/solución** y vaya a la **GettingStarted** solución ha creado anteriormente (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="c559e-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="c559e-119">Seleccione **abierto**.</span><span class="sxs-lookup"><span data-stu-id="c559e-119">Select **Open**.</span></span>

    2. <span data-ttu-id="c559e-120">Desde el **vista** menú, seleccione **el Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="c559e-120">From the **View** menu, select **Solution Explorer**.</span></span>
    
    3. <span data-ttu-id="c559e-121">En el **el Explorador de soluciones** ventana, seleccione el **GettingStarted** (nodo superior) de la solución y, a continuación, seleccione **agregar** > **denuevoproyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="c559e-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 

    4. <span data-ttu-id="c559e-122">En el **Agregar nuevo proyecto** ventana, en el lado izquierdo, seleccione el **Windows Desktop** categoría **Visual C#**  o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="c559e-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="c559e-123">Seleccione el **aplicación de consola (.NET Framework)** plantilla y escriba *GettingStartedHost* para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="c559e-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="c559e-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c559e-124">Select **OK**.</span></span>

2. <span data-ttu-id="c559e-125">Agregue una referencia en el **GettingStartedHost** proyecto a la **GettingStartedLib** proyecto:</span><span class="sxs-lookup"><span data-stu-id="c559e-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span> 

    1. <span data-ttu-id="c559e-126">En el **el Explorador de soluciones** ventana, seleccione el **referencias** carpeta bajo la **GettingStartedHost** proyecto y, a continuación, seleccione **Agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="c559e-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="c559e-127">En el **Agregar referencia** cuadro de diálogo, en **proyectos** en el lado izquierdo de la ventana, seleccione **solución**.</span><span class="sxs-lookup"><span data-stu-id="c559e-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span> 
 
    3. <span data-ttu-id="c559e-128">Seleccione **GettingStartedLib** en la sección central de la ventana y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c559e-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span> 

       <span data-ttu-id="c559e-129">Esta acción impide que los tipos definidos en el **GettingStartedLib** proyecto esté disponible para el **GettingStartedHost** proyecto.</span><span class="sxs-lookup"><span data-stu-id="c559e-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="c559e-130">Agregue una referencia en el **GettingStartedHost** proyecto a la <xref:System.ServiceModel> ensamblado:</span><span class="sxs-lookup"><span data-stu-id="c559e-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="c559e-131">En el **el Explorador de soluciones** ventana, seleccione el **referencias** carpeta bajo la **GettingStartedHost** proyecto y, a continuación, seleccione **Agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="c559e-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>
    
    2. <span data-ttu-id="c559e-132">En el **Agregar referencia** ventana, en **ensamblados** en el lado izquierdo de la ventana, seleccione **Framework**.</span><span class="sxs-lookup"><span data-stu-id="c559e-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span> 

    3. <span data-ttu-id="c559e-133">Seleccione **System.ServiceModel**y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c559e-133">Select **System.ServiceModel**, and then select **OK**.</span></span> 
    
    4. <span data-ttu-id="c559e-134">Guarde la solución seleccionando **archivo** > **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="c559e-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="c559e-135">Agregue código para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="c559e-135">Add code to host the service</span></span>

<span data-ttu-id="c559e-136">Para hospedar el servicio, agregue código para realizar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c559e-136">To host the service, you add code to do the following steps:</span></span> 
   1. <span data-ttu-id="c559e-137">Crear un URI para la dirección base.</span><span class="sxs-lookup"><span data-stu-id="c559e-137">Create a URI for the base address.</span></span>
   2. <span data-ttu-id="c559e-138">Cree una instancia de clase para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-138">Create a class instance for hosting the service.</span></span>
   3. <span data-ttu-id="c559e-139">Crear un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-139">Create a service endpoint.</span></span>
   4. <span data-ttu-id="c559e-140">Habilitar el intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="c559e-140">Enable metadata exchange.</span></span>
   5. <span data-ttu-id="c559e-141">Abra el host de servicio para escuchar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="c559e-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="c559e-142">Realice los cambios siguientes en el código:</span><span class="sxs-lookup"><span data-stu-id="c559e-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="c559e-143">Abra el **Program.cs** o **Module1.vb** de archivos en el **GettingStartedHost** del proyecto y reemplace su código con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c559e-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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
    
    <span data-ttu-id="c559e-144">Para obtener información sobre cómo funciona este código, consulte [servicio de hospedaje de los pasos del programa](#service-hosting-program-steps).</span><span class="sxs-lookup"><span data-stu-id="c559e-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="c559e-145">Actualice las propiedades del proyecto:</span><span class="sxs-lookup"><span data-stu-id="c559e-145">Update the project properties:</span></span>

   1. <span data-ttu-id="c559e-146">En el **el Explorador de soluciones** ventana, seleccione el **GettingStartedHost** carpeta y, a continuación, seleccione **propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="c559e-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="c559e-147">En el **GettingStartedHost** página de propiedades, seleccione la **aplicación** pestaña:</span><span class="sxs-lookup"><span data-stu-id="c559e-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="c559e-148">Para C# proyectos, seleccionados **GettingStartedHost.Program** desde el **objeto Startup** lista.</span><span class="sxs-lookup"><span data-stu-id="c559e-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="c559e-149">Para proyectos de Visual Basic, seleccione **Service.Program** desde el **objeto Startup** lista.</span><span class="sxs-lookup"><span data-stu-id="c559e-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="c559e-150">Desde el **archivo** menú, seleccione **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="c559e-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="c559e-151">Compruebe que el servicio funciona.</span><span class="sxs-lookup"><span data-stu-id="c559e-151">Verify the service is working</span></span>

1. <span data-ttu-id="c559e-152">Compile la solución y, a continuación, ejecute el **GettingStartedHost** consola de aplicación desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c559e-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span> 

    <span data-ttu-id="c559e-153">El servicio se debe ejecutar con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="c559e-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="c559e-154">Dado que al abrir Visual Studio con privilegios de administrador, al ejecutar **GettingStartedHost** en Visual Studio, la aplicación se ejecuta con privilegios de administrador también.</span><span class="sxs-lookup"><span data-stu-id="c559e-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="c559e-155">Como alternativa, puede abrir un nuevo símbolo del sistema como administrador (seleccione **más** > **ejecutar como administrador** en el menú contextual) y ejecute **GettingStartedHost.exe**  dentro de él.</span><span class="sxs-lookup"><span data-stu-id="c559e-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="c559e-156">Abra un explorador web y vaya a la página del servicio en `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="c559e-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="c559e-157">Servicios como este requieren el permiso adecuado para registrar las direcciones HTTP en el equipo para realizar escuchas.</span><span class="sxs-lookup"><span data-stu-id="c559e-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="c559e-158">Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP.</span><span class="sxs-lookup"><span data-stu-id="c559e-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="c559e-159">Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="c559e-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> 

## <a name="service-hosting-program-steps"></a><span data-ttu-id="c559e-160">Pasos de programa de hospedaje de servicio</span><span class="sxs-lookup"><span data-stu-id="c559e-160">Service hosting program steps</span></span>

<span data-ttu-id="c559e-161">Los pasos en el código agregado para hospedar el servicio se describen como sigue:</span><span class="sxs-lookup"><span data-stu-id="c559e-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="c559e-162">**Paso 1**: Cree una instancia de la `Uri` clase para contener la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="c559e-163">Una dirección URL que contiene una dirección base tiene un URI opcional que identifica un servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="c559e-164">La dirección base es el siguiente formato: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span><span class="sxs-lookup"><span data-stu-id="c559e-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="c559e-165">La dirección base para el servicio de calculadora usa el transporte HTTP, localhost, puerto 8000 y el segmento del URI, GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="c559e-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="c559e-166">**Paso 2**: Cree una instancia de la <xref:System.ServiceModel.ServiceHost> (clase), que se utiliza para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="c559e-167">El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="c559e-168">**Paso 3**: Cree una instancia <xref:System.ServiceModel.Description.ServiceEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="c559e-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="c559e-169">Un extremo de servicio consta de una dirección, un enlace y un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="c559e-170">El <xref:System.ServiceModel.Description.ServiceEndpoint> constructor se compone de una dirección, un enlace y el tipo de interfaz de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="c559e-171">El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="c559e-172">El enlace para este ejemplo es <xref:System.ServiceModel.WSHttpBinding>, que es un enlace integrado y se conecta a puntos de conexión que cumplen con WS-\* especificaciones.</span><span class="sxs-lookup"><span data-stu-id="c559e-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="c559e-173">Para obtener más información sobre los enlaces de WCF, vea [información general sobre los enlaces de WCF](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c559e-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="c559e-174">Anexe la dirección a la dirección base para identificar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="c559e-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="c559e-175">El código especifica la dirección como CalculatorService y la dirección completa para el punto de conexión como `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="c559e-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c559e-176">Para .NET Framework versión 4 y versiones posteriores, la adición de un extremo de servicio es opcional.</span><span class="sxs-lookup"><span data-stu-id="c559e-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="c559e-177">Para estas versiones, si no agrega el código o configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="c559e-178">Para obtener más información sobre los puntos de conexión predeterminados, consulte [especificando una dirección de extremo](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="c559e-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="c559e-179">Para obtener más información acerca de los puntos de conexión de forma predeterminada, los enlaces y comportamientos, consulte [configuración simplificada](simplified-configuration.md) y [configuración simplificada para los servicios WCF](samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c559e-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="c559e-180">**Paso 4**: Habilitar el intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="c559e-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="c559e-181">Los clientes usan el intercambio de metadatos para generar a los servidores proxy para llamar a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="c559e-182">Para habilitar el intercambio de metadatos, cree un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> de instancia, establezca su <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> propiedad a `true`y agregue el `ServiceMetadataBehavior` objeto a la <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> colección de la <xref:System.ServiceModel.ServiceHost> instancia.</span><span class="sxs-lookup"><span data-stu-id="c559e-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="c559e-183">**Paso 5**: Abra <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="c559e-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="c559e-184">La aplicación espera a que presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="c559e-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="c559e-185">Una vez que crea una instancia de la aplicación <xref:System.ServiceModel.ServiceHost>, ejecuta un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="c559e-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="c559e-186">Para obtener más información sobre cómo detectar de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost>, consulte [uso cierre y anulación para liberar los recursos del cliente WCF](samples/use-close-abort-release-wcf-client-resources.md).</span><span class="sxs-lookup"><span data-stu-id="c559e-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c559e-187">Cuando se agrega una biblioteca de servicios WCF, Visual Studio se hospeda automáticamente si depura iniciando un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="c559e-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="c559e-188">Para evitar conflictos, puede impedir que Visual Studio hospeda la biblioteca de servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="c559e-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span> 
> 1. <span data-ttu-id="c559e-189">Seleccione el **GettingStartedLib** proyecto **el Explorador de soluciones** y elija **propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="c559e-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="c559e-190">Seleccione **opciones WCF** y desactive la opción **iniciar Host del servicio WCF al depurar otro proyecto en la misma solución**.</span><span class="sxs-lookup"><span data-stu-id="c559e-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c559e-191">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c559e-191">Next steps</span></span>

<span data-ttu-id="c559e-192">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="c559e-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="c559e-193">Crear y configurar un proyecto de aplicación de consola para hospedar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c559e-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="c559e-194">Agregue código para hospedar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c559e-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="c559e-195">Actualice el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c559e-195">Update the configuration file.</span></span>
> - <span data-ttu-id="c559e-196">Inicie el servicio WCF y compruebe se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c559e-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="c559e-197">En el siguiente tutorial para aprender a crear a un cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="c559e-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c559e-198">Tutorial: Crear a un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="c559e-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
