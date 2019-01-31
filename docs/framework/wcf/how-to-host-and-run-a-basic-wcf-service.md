---
title: Cómo hospedar y ejecutar un servicio básico de Windows Communication Foundation
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 3a029ef23ba3e9a0dd62e410739fa8734acc202a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277776"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="8936f-102">Cómo hospedar y ejecutar un servicio básico de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8936f-102">How to host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="8936f-103">Esta es la tercera de las seis tareas necesarias para crear una aplicación de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8936f-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="8936f-104">Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="8936f-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="8936f-105">En este tema se describe cómo hospedar un servicio de Windows Communication Foundation (WCF) en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="8936f-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="8936f-106">Este procedimiento consta de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8936f-106">This procedure consists of the following steps:</span></span>

- <span data-ttu-id="8936f-107">Cree un proyecto de aplicación de consola para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="8936f-107">Create a console application project to host the service.</span></span>

- <span data-ttu-id="8936f-108">Crear un host del servicio para el servicio.</span><span class="sxs-lookup"><span data-stu-id="8936f-108">Create a service host for the service.</span></span>

- <span data-ttu-id="8936f-109">Habilitar el intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="8936f-109">Enable metadata exchange.</span></span>

- <span data-ttu-id="8936f-110">Abrir el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="8936f-110">Open the service host.</span></span>

<span data-ttu-id="8936f-111">En el ejemplo que se ofrece después del procedimiento, se proporciona una lista completa del código escrito en esta tarea.</span><span class="sxs-lookup"><span data-stu-id="8936f-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>

## <a name="create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="8936f-112">Cree una nueva aplicación de consola para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="8936f-112">Create a new console application to host the service</span></span>

1. <span data-ttu-id="8936f-113">Crear un nuevo proyecto de aplicación de consola en Visual Studio con el botón secundario en la solución introducción y seleccionando **agregar** > **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="8936f-113">Create a new Console Application project in Visual Studio by right-clicking on the Getting Started solution and selecting **Add** > **New Project**.</span></span> <span data-ttu-id="8936f-114">En el **Agregar nuevo proyecto** cuadro de diálogo, en el lado izquierdo, seleccione el **Windows Desktop** categoría **Visual C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="8936f-114">In the **Add New Project** dialog, on the left-hand side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> <span data-ttu-id="8936f-115">Seleccione el **aplicación de consola (.NET Framework)** plantilla y, a continuación, denomine el proyecto **GettingStartedHost**.</span><span class="sxs-lookup"><span data-stu-id="8936f-115">Select the **Console App (.NET Framework)** template, and then name the project **GettingStartedHost**.</span></span>

2. <span data-ttu-id="8936f-116">Agregue una referencia al proyecto GettingStartedLib al proyecto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="8936f-116">Add a reference to the GettingStartedLib project to the GettingStartedHost project.</span></span> <span data-ttu-id="8936f-117">Haga doble clic en el **referencias** carpeta bajo el proyecto GettingStartedHost en **el Explorador de soluciones**y, a continuación, seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="8936f-117">Right-click on the **References** folder under the GettingStartedHost project in **Solution Explorer**, and then select **Add Reference**.</span></span> <span data-ttu-id="8936f-118">En el **Agregar referencia** cuadro de diálogo, seleccione **solución** en el lado izquierdo del cuadro de diálogo, seleccione GettingStartedLib en la sección central del cuadro de diálogo y, a continuación, elija **agregar**.</span><span class="sxs-lookup"><span data-stu-id="8936f-118">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog, select GettingStartedLib in the center section of the dialog, and then choose **Add**.</span></span> <span data-ttu-id="8936f-119">Esto hace que los tipos definidos en GettingStartedLib estén disponibles para el proyecto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="8936f-119">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>

3. <span data-ttu-id="8936f-120">Agregue una referencia a System.ServiceModel al proyecto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="8936f-120">Add a reference to System.ServiceModel to the GettingStartedHost project.</span></span> <span data-ttu-id="8936f-121">Haga clic en el **referencias** carpeta bajo el proyecto GettingStartedHost en **el Explorador de soluciones** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="8936f-121">Right-click the **References** folder under the GettingStartedHost project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="8936f-122">En el **Agregar referencia** cuadro de diálogo, seleccione **Framework** en el lado izquierdo del cuadro de diálogo **ensamblados**.</span><span class="sxs-lookup"><span data-stu-id="8936f-122">In the **Add Reference** dialog, select **Framework** on the left-hand side of the dialog under **Assemblies**.</span></span> <span data-ttu-id="8936f-123">Busque y seleccione **System.ServiceModel**y, a continuación, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8936f-123">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> <span data-ttu-id="8936f-124">Guarde la solución seleccionando **archivo** > **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="8936f-124">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="host-the-service"></a><span data-ttu-id="8936f-125">El servicio de host</span><span class="sxs-lookup"><span data-stu-id="8936f-125">Host the service</span></span>

<span data-ttu-id="8936f-126">Abra el archivo Program.cs o Module.vb y escriba el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="8936f-126">Open the Program.cs or Module.vb file and enter the following code:</span></span>

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
            // Step 1 Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 Create a ServiceHost instance
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 Start the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 Create a URI to serve as the base address
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")

            ' Step 2 Create a ServiceHost instance
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
           Try

                ' Step 3 Add a service endpoint
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 Enable metadata exchange.
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 Start the service
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

<span data-ttu-id="8936f-127">**Paso 1** -crea una instancia de la clase de Uri que contenga la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="8936f-127">**Step 1** - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="8936f-128">Los servicios se identifican mediante una dirección URL que contiene una dirección base y un URI opcional.</span><span class="sxs-lookup"><span data-stu-id="8936f-128">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="8936f-129">Se da formato a la dirección base como sigue: [transporte]://[nombre de equipo o dominio][:nº de puerto opcional]/[segmento opcional de URI]La dirección base para el servicio de calculadora usa el transporte HTTP, localhost, el puerto 8000 y el segmento de URI "GettingStarted".</span><span class="sxs-lookup"><span data-stu-id="8936f-129">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>

<span data-ttu-id="8936f-130">**Paso 2** : crea una instancia de la <xref:System.ServiceModel.ServiceHost> clase para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="8936f-130">**Step 2** – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="8936f-131">El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="8936f-131">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>

<span data-ttu-id="8936f-132">**Paso 3** – crea un <xref:System.ServiceModel.Description.ServiceEndpoint> instancia.</span><span class="sxs-lookup"><span data-stu-id="8936f-132">**Step 3** – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="8936f-133">Un punto de conexión de servicio consta de una dirección, un enlace y un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="8936f-133">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="8936f-134">Por tanto, el constructor <xref:System.ServiceModel.Description.ServiceEndpoint> toma el tipo de interfaz del contrato de servicio, un enlace y una dirección.</span><span class="sxs-lookup"><span data-stu-id="8936f-134">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="8936f-135">El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="8936f-135">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="8936f-136">El enlace usado en este ejemplo es <xref:System.ServiceModel.WSHttpBinding>, que es un enlace integrado que se emplea para conectarse a puntos de conexión que son conformes a las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="8936f-136">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="8936f-137">Para obtener más información sobre los enlaces de WCF, vea [Información general de enlaces de Windows Communication Foundation](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8936f-137">For more information about WCF bindings, see [WCF Bindings Overview](bindings-overview.md).</span></span> <span data-ttu-id="8936f-138">La dirección se anexa a la dirección base para identificar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8936f-138">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="8936f-139">La dirección especificada en este código es "CalculatorService", por lo que es la dirección completa para el punto de conexión `"http://localhost:8000/GettingStarted/CalculatorService"`.</span><span class="sxs-lookup"><span data-stu-id="8936f-139">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"`.</span></span>

    > [!IMPORTANT]
    > Adding a service endpoint is optional when using .NET Framework 4 or later. In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service. For more information about default endpoints see [Specifying an Endpoint Address](specifying-an-endpoint-address.md). For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).

<span data-ttu-id="8936f-140">**Paso 4** : habilitar el intercambio de metadatos.</span><span class="sxs-lookup"><span data-stu-id="8936f-140">**Step 4** – Enable metadata exchange.</span></span> <span data-ttu-id="8936f-141">Los clientes usarán intercambio de metadatos para generar los servidores proxy que se usarán para llamar a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="8936f-141">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="8936f-142">Para habilitar el intercambio de metadatos, cree una instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, establezca su propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true` y agregue el comportamiento a la colección <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> de la instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="8936f-142">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

<span data-ttu-id="8936f-143">**Paso 5** : abra el <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="8936f-143">**Step 5** – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="8936f-144">Observe que el código espera que el usuario presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8936f-144">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="8936f-145">Si no lo hace, la aplicación se cerrará inmediatamente y el servicio se cerrará. Observe también que se usa un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="8936f-145">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="8936f-146">Una vez creada la instancia de <xref:System.ServiceModel.ServiceHost>, el resto del código se coloca en un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="8936f-146">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="8936f-147">Para obtener más información sobre cómo detectar de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost>, consulte [uso cierre y anulación para liberar los recursos del cliente WCF](samples/use-close-abort-release-wcf-client-resources.md)</span><span class="sxs-lookup"><span data-stu-id="8936f-147">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8936f-148">Edición de App.config en GettingStartedLib para reflejar los cambios realizados en el código:</span><span class="sxs-lookup"><span data-stu-id="8936f-148">Edit App.config in GettingStartedLib to reflect the changes made in code:</span></span>
> 1. <span data-ttu-id="8936f-149">Cambie la línea 14 a `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="8936f-149">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
> 2. <span data-ttu-id="8936f-150">Cambie la línea 17 a `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="8936f-150">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
> 3. <span data-ttu-id="8936f-151">Cambie la línea 22 en `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="8936f-151">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="8936f-152">Compruebe que el servicio funciona.</span><span class="sxs-lookup"><span data-stu-id="8936f-152">Verify the service is working</span></span>

1. <span data-ttu-id="8936f-153">Ejecutar la consola GettingStartedHost aplicación desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8936f-153">Run the GettingStartedHost console application from inside Visual Studio.</span></span>

   <span data-ttu-id="8936f-154">El servicio se debe ejecutar con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="8936f-154">The service must be run with administrator privileges.</span></span> <span data-ttu-id="8936f-155">Dado que Visual Studio se ha abierto con privilegios de administrador, GettingStartedHost también se ejecuta con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="8936f-155">Because Visual Studio was opened with administrator privileges, GettingStartedHost is also run with administrator privileges.</span></span> <span data-ttu-id="8936f-156">También puede abrir un nuevo símbolo del sistema mediante **ejecutar como administrador** y ejecute service.exe desde allí.</span><span class="sxs-lookup"><span data-stu-id="8936f-156">You can also open a new command prompt using **Run as administrator** and run service.exe within it.</span></span>

2. <span data-ttu-id="8936f-157">Abra un explorador web y vaya a la página de depuración del servicio en `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="8936f-157">Open a web browser and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

## <a name="example"></a><span data-ttu-id="8936f-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8936f-158">Example</span></span>

<span data-ttu-id="8936f-159">El siguiente ejemplo incluye el contrato de servicios y la implementación de los pasos anteriores del tutorial y hospeda el servicio en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="8936f-159">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>

<span data-ttu-id="8936f-160">Para compilar esto con un compilador de línea de comandos, compile IService1.cs y Service1.cs en una biblioteca de clases que hace referencia a `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="8936f-160">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library that references `System.ServiceModel.dll`.</span></span> <span data-ttu-id="8936f-161">Compile Program.cs como una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="8936f-161">Compile Program.cs as a console application.</span></span>

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
        public interface ICalculator
        {
            [OperationContract]
            double Add(double n1, double n2);
            [OperationContract]
            double Subtract(double n1, double n2);
            [OperationContract]
            double Multiply(double n1, double n2);
            [OperationContract]
            double Divide(double n1, double n2);
        }
}
```

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

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
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/ServiceModelSamples/Service");

            // Step 2 of the hosting procedure: Create ServiceHost
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 of the hosting procedure: Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 of the hosting procedure: Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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

Namespace GettingStartedLib

    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
    Public Interface ICalculator

        <OperationContract()> _
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
End Namespace
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")

            ' Step 2 of the hosting procedure: Create ServiceHost
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
            Try

                ' Step 3 of the hosting procedure: Add a service endpoint.
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 of the hosting procedure: Enable metadata exchange.
                ' Enable metadata exchange
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

> [!NOTE]
> <span data-ttu-id="8936f-162">Servicios como este requieren permiso para registrar las direcciones HTTP en el equipo para la realización de escuchas.</span><span class="sxs-lookup"><span data-stu-id="8936f-162">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="8936f-163">Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP.</span><span class="sxs-lookup"><span data-stu-id="8936f-163">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="8936f-164">Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="8936f-164">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="8936f-165">Cuando se ejecuta en Visual Studio, service.exe se debe ejecutar con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="8936f-165">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8936f-166">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8936f-166">Next steps</span></span>

<span data-ttu-id="8936f-167">Ahora, el servicio se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="8936f-167">Now the service is running.</span></span> <span data-ttu-id="8936f-168">En la siguiente tarea, creará a un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="8936f-168">In the next task, you create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8936f-169">Cómo: Crear a un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="8936f-169">How to: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)

<span data-ttu-id="8936f-170">Para obtener información de solución de problemas, vea [Solución de problemas con el tutorial de introducción](troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="8936f-170">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](troubleshooting-the-getting-started-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8936f-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="8936f-171">See also</span></span>

- [<span data-ttu-id="8936f-172">Introducción</span><span class="sxs-lookup"><span data-stu-id="8936f-172">Getting Started</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="8936f-173">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="8936f-173">Self-Host</span></span>](samples/self-host.md)