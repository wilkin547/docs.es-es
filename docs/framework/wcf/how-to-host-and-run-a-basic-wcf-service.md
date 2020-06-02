---
title: 'Tutorial: hospedar y ejecutar un servicio de Windows Communication Foundation básico'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 872844487578843492e05dd2abb87b50e0bec91c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291401"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="ff084-102">Tutorial: hospedar y ejecutar un servicio de Windows Communication Foundation básico</span><span class="sxs-lookup"><span data-stu-id="ff084-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="ff084-103">En este tutorial se describe el tercer de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ff084-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="ff084-104">Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ff084-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="ff084-105">La siguiente tarea para crear una aplicación WCF es hospedar un servicio WCF en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="ff084-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="ff084-106">Un servicio WCF expone uno o más *puntos de conexión*, cada uno de los cuales expone una o más operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="ff084-107">Un punto de conexión de servicio especifica la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="ff084-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="ff084-108">Una dirección donde puede encontrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-108">An address where you can find the service.</span></span>
- <span data-ttu-id="ff084-109">Un enlace que contiene la información que describe cómo un cliente debe comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-109">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="ff084-110">Un contrato que define la funcionalidad que proporciona el servicio a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="ff084-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="ff084-111">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="ff084-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ff084-112">Cree y configure un proyecto de aplicación de consola para hospedar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ff084-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="ff084-113">Agregue código para hospedar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ff084-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="ff084-114">Actualice el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ff084-114">Update the configuration file.</span></span>
> - <span data-ttu-id="ff084-115">Inicie el servicio WCF y compruebe que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="ff084-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="ff084-116">Crear y configurar un proyecto de aplicación de consola para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="ff084-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="ff084-117">Cree un proyecto de aplicación de consola en Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="ff084-117">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="ff084-118">En el menú **archivo** , seleccione **abrir**  >  **proyecto o solución** y busque la solución **gettingstarted** que creó anteriormente (*gettingstarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="ff084-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="ff084-119">Selecciona **Open** (Abrir).</span><span class="sxs-lookup"><span data-stu-id="ff084-119">Select **Open**.</span></span>

    2. <span data-ttu-id="ff084-120">En el menú **Ver** , seleccione **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="ff084-120">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="ff084-121">En la ventana **Explorador de soluciones** , seleccione la solución **gettingstarted** (nodo superior) y, a continuación, seleccione **Agregar**  >  **nuevo proyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="ff084-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="ff084-122">En la ventana **Agregar nuevo proyecto** , en el lado izquierdo, seleccione la categoría **escritorio de Windows** en **Visual C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="ff084-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="ff084-123">Seleccione la plantilla **aplicación de consola (.NET Framework)** y escriba *GettingStartedHost* para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="ff084-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="ff084-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff084-124">Select **OK**.</span></span>

2. <span data-ttu-id="ff084-125">Agregue una referencia en el proyecto **GettingStartedHost** al proyecto **GettingStartedLib** :</span><span class="sxs-lookup"><span data-stu-id="ff084-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="ff084-126">En la ventana **Explorador de soluciones** , seleccione la carpeta **referencias** en el proyecto **GettingStartedHost** y, a continuación, seleccione **Agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="ff084-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="ff084-127">En el cuadro de diálogo **Agregar referencia** , en **proyectos** en el lado izquierdo de la ventana, seleccione **solución**.</span><span class="sxs-lookup"><span data-stu-id="ff084-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="ff084-128">Seleccione **GettingStartedLib** en la sección central de la ventana y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff084-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="ff084-129">Esta acción hace que los tipos definidos en el proyecto **GettingStartedLib** estén disponibles para el proyecto **GettingStartedHost** .</span><span class="sxs-lookup"><span data-stu-id="ff084-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="ff084-130">Agregue una referencia en el proyecto **GettingStartedHost** al <xref:System.ServiceModel> ensamblado:</span><span class="sxs-lookup"><span data-stu-id="ff084-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="ff084-131">En la ventana **Explorador de soluciones** , seleccione la carpeta **referencias** en el proyecto **GettingStartedHost** y, a continuación, seleccione **Agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="ff084-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="ff084-132">En la ventana **Agregar referencia** , en **ensamblados** en el lado izquierdo de la ventana, seleccione **marco de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ff084-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="ff084-133">Seleccione **System. ServiceModel**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff084-133">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="ff084-134">Guarde la solución seleccionando **archivo**  >  **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="ff084-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="ff084-135">Agregar código para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="ff084-135">Add code to host the service</span></span>

<span data-ttu-id="ff084-136">Para hospedar el servicio, agregue código para realizar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff084-136">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="ff084-137">Cree un URI para la dirección base.</span><span class="sxs-lookup"><span data-stu-id="ff084-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="ff084-138">Cree una instancia de clase para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="ff084-139">Cree un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="ff084-140">Habilitar el intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="ff084-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="ff084-141">Abra el host del servicio para escuchar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="ff084-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="ff084-142">Realice los siguientes cambios en el código:</span><span class="sxs-lookup"><span data-stu-id="ff084-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="ff084-143">Abra el archivo **Program.CS** o **Module1. VB** en el proyecto **GettingStartedHost** y reemplace su código por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff084-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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
                    selfHost.Description.Behaviors.Add(smb);

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

    <span data-ttu-id="ff084-144">Para obtener información sobre cómo funciona este código, vea [pasos del programa de hospedaje de servicios](#service-hosting-program-steps).</span><span class="sxs-lookup"><span data-stu-id="ff084-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="ff084-145">Actualice las propiedades del proyecto:</span><span class="sxs-lookup"><span data-stu-id="ff084-145">Update the project properties:</span></span>

   1. <span data-ttu-id="ff084-146">En la ventana **Explorador de soluciones** , seleccione la carpeta **GettingStartedHost** y, a continuación, seleccione **propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="ff084-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="ff084-147">En la página Propiedades de **GettingStartedHost** , seleccione la pestaña **aplicación** :</span><span class="sxs-lookup"><span data-stu-id="ff084-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="ff084-148">En el caso de los proyectos de C#, seleccione **GettingStartedHost. Program** en la lista **objeto de inicio** .</span><span class="sxs-lookup"><span data-stu-id="ff084-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="ff084-149">Para proyectos de Visual Basic, seleccione **Service. Program** en la lista **objeto de inicio** .</span><span class="sxs-lookup"><span data-stu-id="ff084-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="ff084-150">En el menú **archivo** , seleccione **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="ff084-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="ff084-151">Comprobar que el servicio funciona</span><span class="sxs-lookup"><span data-stu-id="ff084-151">Verify the service is working</span></span>

1. <span data-ttu-id="ff084-152">Compile la solución y, a continuación, ejecute la aplicación de consola **GettingStartedHost** desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ff084-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="ff084-153">El servicio se debe ejecutar con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="ff084-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="ff084-154">Como abrió Visual Studio con privilegios de administrador, al ejecutar **GettingStartedHost** en Visual Studio, la aplicación se ejecuta también con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="ff084-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="ff084-155">Como alternativa, puede abrir un nuevo símbolo del sistema como administrador (seleccione **más**  >  **Ejecutar como administrador** en el menú contextual) y ejecute **GettingStartedHost. exe** en él.</span><span class="sxs-lookup"><span data-stu-id="ff084-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="ff084-156">Abra un explorador Web y vaya a la página del servicio en `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="ff084-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ff084-157">Los servicios como este requieren el permiso adecuado para registrar las direcciones HTTP en el equipo para realizar escuchas.</span><span class="sxs-lookup"><span data-stu-id="ff084-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="ff084-158">Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP.</span><span class="sxs-lookup"><span data-stu-id="ff084-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="ff084-159">Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="ff084-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="ff084-160">Pasos del programa de hospedaje del servicio</span><span class="sxs-lookup"><span data-stu-id="ff084-160">Service hosting program steps</span></span>

<span data-ttu-id="ff084-161">Los pasos del código que agregó para hospedar el servicio se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="ff084-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="ff084-162">**Paso 1**: cree una instancia de la `Uri` clase para que contenga la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="ff084-163">Una dirección URL que contiene una dirección base tiene un URI opcional que identifica un servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="ff084-164">La dirección base tiene el formato siguiente: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>` .</span><span class="sxs-lookup"><span data-stu-id="ff084-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="ff084-165">La dirección base para el servicio de calculadora usa el transporte HTTP, localhost, el puerto 8000 y el segmento del URI, GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="ff084-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="ff084-166">**Paso 2**: crear una instancia de la <xref:System.ServiceModel.ServiceHost> clase, que se utiliza para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="ff084-167">El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="ff084-168">**Paso 3**: crear una <xref:System.ServiceModel.Description.ServiceEndpoint> instancia de.</span><span class="sxs-lookup"><span data-stu-id="ff084-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="ff084-169">Un extremo de servicio consta de una dirección, un enlace y un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="ff084-170">El <xref:System.ServiceModel.Description.ServiceEndpoint> constructor se compone del tipo de interfaz del contrato de servicio, un enlace y una dirección.</span><span class="sxs-lookup"><span data-stu-id="ff084-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="ff084-171">El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="ff084-172">El enlace para este ejemplo es <xref:System.ServiceModel.WSHttpBinding> , que es un enlace integrado y se conecta a puntos de conexión que cumplen con las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="ff084-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="ff084-173">Para obtener más información sobre los enlaces de WCF, consulte [información general](bindings-overview.md)sobre los enlaces de WCF.</span><span class="sxs-lookup"><span data-stu-id="ff084-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="ff084-174">La dirección se anexa a la dirección base para identificar el extremo.</span><span class="sxs-lookup"><span data-stu-id="ff084-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="ff084-175">El código especifica la dirección como CalculatorService y la dirección completa del extremo como `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="ff084-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ff084-176">Para .NET Framework versión 4 y versiones posteriores, la adición de un punto de conexión de servicio es opcional.</span><span class="sxs-lookup"><span data-stu-id="ff084-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="ff084-177">Para estas versiones, si no agrega el código o la configuración, WCF agrega un extremo predeterminado para cada combinación de dirección base y contrato implementada por el servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="ff084-178">Para obtener más información sobre los puntos de conexión predeterminados, vea [especificar una dirección de extremo](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="ff084-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="ff084-179">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [configuración simplificada](simplified-configuration.md) y [configuración simplificada para servicios WCF](samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ff084-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="ff084-180">**Paso 4**: habilitar el intercambio de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ff084-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="ff084-181">Los clientes utilizan el intercambio de metadatos para generar servidores proxy para llamar a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="ff084-182">Para habilitar el intercambio de metadatos, cree una <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instancia de, establezca su <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> propiedad en `true` y agregue el `ServiceMetadataBehavior` objeto a la <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> colección de la <xref:System.ServiceModel.ServiceHost> instancia.</span><span class="sxs-lookup"><span data-stu-id="ff084-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="ff084-183">**Paso 5**: Abra <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="ff084-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="ff084-184">La aplicación espera a que presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="ff084-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="ff084-185">Una vez que se crea una instancia de la aplicación <xref:System.ServiceModel.ServiceHost> , se ejecuta un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="ff084-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="ff084-186">Para obtener más información sobre cómo detectar de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost> , vea [usar Close y Abort para liberar los recursos de cliente de WCF](samples/use-close-abort-release-wcf-client-resources.md).</span><span class="sxs-lookup"><span data-stu-id="ff084-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff084-187">Cuando se agrega una biblioteca de servicios WCF, Visual Studio la hospeda automáticamente si se inicia un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="ff084-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="ff084-188">Para evitar conflictos, puede evitar que Visual Studio hospede la biblioteca de servicios de WCF.</span><span class="sxs-lookup"><span data-stu-id="ff084-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="ff084-189">Seleccione el proyecto **GettingStartedLib** en **Explorador de soluciones** y elija **propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="ff084-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="ff084-190">Seleccione **Opciones de WCF** y desactive **iniciar host de servicio WCF al depurar otro proyecto en la misma solución**.</span><span class="sxs-lookup"><span data-stu-id="ff084-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ff084-191">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ff084-191">Next steps</span></span>

<span data-ttu-id="ff084-192">En este tutorial, ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="ff084-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ff084-193">Cree y configure un proyecto de aplicación de consola para hospedar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ff084-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="ff084-194">Agregue código para hospedar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="ff084-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="ff084-195">Actualice el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ff084-195">Update the configuration file.</span></span>
> - <span data-ttu-id="ff084-196">Inicie el servicio WCF y compruebe que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="ff084-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="ff084-197">Avance al siguiente tutorial para aprender a crear un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="ff084-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ff084-198">Tutorial: crear un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="ff084-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
