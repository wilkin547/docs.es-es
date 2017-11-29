---
title: "Procedimiento para hospedar y ejecutar un servicio básico de Windows Communication Foundation"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f0368e2e605f3f5c5b5a7b0d8c05f7276d8df22d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="2b5b5-102">Procedimiento para hospedar y ejecutar un servicio básico de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="2b5b5-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>
<span data-ttu-id="2b5b5-103">Es la tercera de las seis tareas necesarias para crear una aplicación de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b5b5-103">This is the third of six tasks required to create a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="2b5b5-104">Para obtener información general de las seis de las tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="2b5b5-105">Este tema describe cómo hospedar un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-105">This topic describes how to host a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service in a console application.</span></span> <span data-ttu-id="2b5b5-106">Este procedimiento consta de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="2b5b5-106">This procedure consists of the following steps:</span></span>  
  
-   <span data-ttu-id="2b5b5-107">Cree un proyecto de aplicación de consola para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-107">Create a console application project to host the service.</span></span>  
  
-   <span data-ttu-id="2b5b5-108">Crear un host del servicio para el servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-108">Create a service host for the service.</span></span>  
  
-   <span data-ttu-id="2b5b5-109">Habilitar el intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="2b5b5-109">Enable metadata exchange.</span></span>  
  
-   <span data-ttu-id="2b5b5-110">Abrir el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-110">Open the service host.</span></span>  
  
 <span data-ttu-id="2b5b5-111">En el ejemplo que se ofrece después del procedimiento, se proporciona una lista completa del código escrito en esta tarea.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="2b5b5-112">Para crear una nueva aplicación de consola para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="2b5b5-112">To create a new console application to host the service</span></span>  
  
1.  <span data-ttu-id="2b5b5-113">Crear un nuevo proyecto de aplicación de consola con el botón secundario en la solución introducción, seleccionar, **agregar**, **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-113">Create a new Console Application project by right-clicking on the Getting Started solution, selecting, **Add**, **New Project**.</span></span> <span data-ttu-id="2b5b5-114">En el **Agregar nuevo proyecto** cuadro de diálogo en el lado izquierdo del cuadro de diálogo, seleccione **Windows** en **C#** o **VB**.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-114">In the **Add New Project** dialog on the left hand side of the dialog select **Windows** under **C#** or **VB**.</span></span> <span data-ttu-id="2b5b5-115">En la sección central del cuadro de diálogo Seleccionar **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-115">In the center section of the dialog select **Console Application**.</span></span> <span data-ttu-id="2b5b5-116">Asigne al proyecto el nombre GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-116">Name the project GettingStartedHost.</span></span>  
  
2.  <span data-ttu-id="2b5b5-117">Establezca la plataforma de destino del proyecto GettingStartedHost en .NET Framework 4.5 haciendo clic en **GettingStartedHost** en el Explorador de soluciones y seleccionando **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-117">Set the target framework of the GettingStartedHost project to .NET Framework 4.5 by right clicking on **GettingStartedHost** in the Solution Explorer and selecting **Properties**.</span></span> <span data-ttu-id="2b5b5-118">En el cuadro desplegable etiquetado **.NET Framework de destino** seleccione **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-118">In the dropdown box labeled **Target Framework** select **.NET Framework 4.5**.</span></span> <span data-ttu-id="2b5b5-119">Establecer la plataforma de destino de un proyecto VB es algo diferente, en el cuadro de diálogo de propiedades de proyecto GettingStartedHost, haga clic en el **compilar** pestaña en el lado izquierdo de la pantalla y, a continuación, haga clic en el **avanzadas a compilar Opciones de** situado en la esquina inferior izquierda del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-119">Setting the target framework for a VB project is a little different, in the GettingStartedHost project properties dialog, click the **Compile** tab on the left-hand side of the screen, and then click the **Advanced Compile Options** button at the lower left-hand corner of the dialog.</span></span> <span data-ttu-id="2b5b5-120">A continuación, seleccione **.NET Framework 4.5** en el cuadro desplegable etiquetado **.NET Framework de destino**.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-120">Then select **.NET Framework 4.5** in the dropdown box labeled **Target Framework**.</span></span>  
  
     <span data-ttu-id="2b5b5-121">Establecer la plataforma de destino hará que [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] para volver a cargar la solución, presione **Aceptar** cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-121">Setting the target framework will cause [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] to reload the solution, press **OK** when prompted.</span></span>  
  
3.  <span data-ttu-id="2b5b5-122">Agregue una referencia al proyecto GettingStartedLib al proyecto GettingStartedHost haciendo clic en el **referencias** carpeta bajo el proyecto GettingStartedHost en el Explorador de soluciones y seleccione **Agregar referencia** .</span><span class="sxs-lookup"><span data-stu-id="2b5b5-122">Add a reference to the GettingStartedLib project to the GettingStartedHost project by right clicking on the **References** folder under the GettingStartedHost project in the solution explorer and select **Add Reference**.</span></span> <span data-ttu-id="2b5b5-123">En el **Agregar referencia** cuadro de diálogo, seleccione **solución** en el lado izquierdo del cuadro de diálogo y seleccione GettingStartedLib en la sección central del cuadro de diálogo y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-123">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog and select GettingStartedLib in the center section of the dialog and click **Add**.</span></span> <span data-ttu-id="2b5b5-124">Esto hace que los tipos definidos en GettingStartedLib estén disponibles para el proyecto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-124">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>  
  
4.  <span data-ttu-id="2b5b5-125">Agregue una referencia a System.ServiceModel al proyecto GettingStartedHost haciendo clic en el **referencia** carpeta bajo el proyecto GettingStartedHost en el Explorador de soluciones y seleccione **agregar** Referencia.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-125">Add a reference to System.ServiceModel to the GettingStartedHost project by right-clicking the **Reference** folder under the GettingStartedHost project in Solution Explorer and select **Add** Reference.</span></span> <span data-ttu-id="2b5b5-126">En el **Agregar referencia** diálogo seleccione **Framework** en el lado izquierdo del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-126">In the **Add Reference** dialog select **Framework** on the left-hand side of the dialog.</span></span> <span data-ttu-id="2b5b5-127">En el cuadro de texto Ensamblados de búsqueda, escriba `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-127">In the Search Assemblies textbox, type in `System.ServiceModel`.</span></span> <span data-ttu-id="2b5b5-128">En la sección central del cuadro de diálogo Seleccionar **System.ServiceModel**, haga clic en el **agregar** y haga clic en el **cerrar** botón.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-128">In the center section of the dialog select **System.ServiceModel**, click the **Add** button, and click the **Close** button.</span></span> <span data-ttu-id="2b5b5-129">Guarde la solución haciendo clic en el botón Guardar todo debajo del menú principal.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-129">Save the solution by clicking the Save All button below the main menu.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="2b5b5-130">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="2b5b5-130">To host the service</span></span>  
  
-   <span data-ttu-id="2b5b5-131">Abra el archivo Program.cs o Module.vb y escriba el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b5b5-131">Open the Program.cs or Module.vb file and enter the following code:</span></span>  
  
    ```csharp
    // program.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
    using GettingStartedLib;  
    using System.ServiceModel.Description;   
  
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
    'Module1.vb  
    Imports System  
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
  
    1.  <span data-ttu-id="2b5b5-132">Paso 1 - Crea una instancia de la clase Uri para contener la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-132">Step 1 - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="2b5b5-133">Los servicios se identifican mediante una dirección URL que contiene una dirección base y un URI opcional.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-133">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="2b5b5-134">Da formato a la dirección base es como sigue: [Transporte] :// [nombre de equipo o dominio] [: opcional º de puerto] / [segmento opcional de URI] la dirección base para el servicio de calculadora usa el transporte HTTP, localhost, puerto 8000 y el segmento de URI "GettingStarted"</span><span class="sxs-lookup"><span data-stu-id="2b5b5-134">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>  
  
    2.  <span data-ttu-id="2b5b5-135">Paso 2 - Crea una instancia de la clase <xref:System.ServiceModel.ServiceHost> para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-135">Step 2 – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="2b5b5-136">El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-136">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>  
  
    3.  <span data-ttu-id="2b5b5-137">Paso 3-crea una <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` instancia.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-137">Step 3 – Creates a <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` instance.</span></span> <span data-ttu-id="2b5b5-138">Un punto de conexión de servicio consta de una dirección, un enlace y un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-138">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="2b5b5-139">El <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` constructor toma, por tanto, el tipo de interfaz de contrato de servicio, un enlace y una dirección.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-139">The <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint`  constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="2b5b5-140">El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-140">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="2b5b5-141">El enlace usado en este ejemplo es <xref:System.ServiceModel.WSHttpBinding>, que es un enlace integrado que se emplea para conectarse a extremos que son conformes a las especificaciones de WS-*.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-141">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-* specifications.</span></span> <span data-ttu-id="2b5b5-142">Para obtener más información sobre los enlaces de WCF, vea [información general de enlaces de WCF](../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2b5b5-142">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="2b5b5-143">La dirección se anexa a la dirección base para identificar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-143">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="2b5b5-144">La dirección especificada en este código es "CalculatorService", por lo que es la dirección completa para el extremo `"http://localhost:8000/GettingStarted/CalculatorService"` agregar un extremo de servicio es opcional cuando se usa .NET Framework 4.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-144">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"` Adding a service endpoint is optional when using .NET Framework 4.0 or later.</span></span> <span data-ttu-id="2b5b5-145">En estas versiones, si no se agrega ningún punto de conexión en el código o en la configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementada por el servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-145">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="2b5b5-146">Para obtener más información sobre predeterminado vea extremos [al especificar una dirección de punto de conexión](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="2b5b5-146">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="2b5b5-147"> los puntos de conexión, enlaces y comportamientos predeterminados, consulte [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="2b5b5-147"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="2b5b5-148">Agregar un punto de conexión de servicio es opcional cuando se usa .NET Framework 4.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-148">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="2b5b5-149">En estas versiones, si no se agrega ningún punto de conexión en el código o en la configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementada por el servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-149">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="2b5b5-150">Para obtener más información sobre predeterminado vea extremos [al especificar una dirección de punto de conexión](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="2b5b5-150">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="2b5b5-151"> los puntos de conexión, enlaces y comportamientos predeterminados, consulte [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="2b5b5-151"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
    4.  <span data-ttu-id="2b5b5-152">Paso 4 - Habilita el intercambio de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-152">Step 4 – Enable metadata exchange.</span></span> <span data-ttu-id="2b5b5-153">Los clientes usarán intercambio de metadatos para generar los servidores proxy que se usarán para llamar a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-153">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="2b5b5-154">Para habilitar el intercambio de metadatos, cree un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> de la instancia, establézcala del <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> propiedad `true`y agregar el comportamiento a la <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  --> `System.ServiceModel.ServiceHost.Behaviors%2A` colección de la <xref:System.ServiceModel.ServiceHost> instancia.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-154">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>  
  
    5.  <span data-ttu-id="2b5b5-155">Paso 5 - Abre <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-155">Step 5 – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="2b5b5-156">Observe que el código espera que el usuario presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-156">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="2b5b5-157">Si no lo hace, la aplicación se cerrará inmediatamente y el servicio se cerrará. Observe también que se usa un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-157">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="2b5b5-158">Una vez creada la instancia de <xref:System.ServiceModel.ServiceHost>, el resto del código se coloca en un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-158">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="2b5b5-159">Para obtener más información sobre la detección de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost>, consulte [evitar problemas con la instrucción Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span><span class="sxs-lookup"><span data-stu-id="2b5b5-159">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span></span>  
  
### <a name="to-verify-the-service-is-working"></a><span data-ttu-id="2b5b5-160">Para comprobar si el servicio funciona</span><span class="sxs-lookup"><span data-stu-id="2b5b5-160">To verify the service is working</span></span>  
  
1.  <span data-ttu-id="2b5b5-161">Ejecute la aplicación de consola GettingStartedHost desde [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b5b5-161">Run the GettingStartedHost console application from inside [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="2b5b5-162">Al ejecutarse en [!INCLUDE[wv](../../../includes/wv-md.md)] y sistemas operativos posteriores, el servicio se debe ejecutar con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-162">When running on [!INCLUDE[wv](../../../includes/wv-md.md)] and later operating systems, the service must be run with administrator privileges.</span></span> <span data-ttu-id="2b5b5-163">Dado que [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] se ejecutó con privilegios de administrador, GettingStartedHost también se ejecuta con dichos privilegios.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-163">Because [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] was run with Administrator privileges, GettingStartedHost is also run with Administrator privileges.</span></span> <span data-ttu-id="2b5b5-164">También puede iniciar un nuevo símbolo del sistema con privilegios de administrador y ejecutar service.exe desde allí.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-164">You can also start a new command prompt running it with Administrator privileges and run service.exe within it.</span></span>  
  
2.  <span data-ttu-id="2b5b5-165">Abra Internet Explorer y busque la página de depuración del servicio en `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-165">Open Internet Explorer and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b5b5-166">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b5b5-166">Example</span></span>  
 <span data-ttu-id="2b5b5-167">El siguiente ejemplo incluye el contrato de servicios y la implementación de los pasos anteriores del tutorial y hospeda el servicio en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-167">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>  
  
 <span data-ttu-id="2b5b5-168">Para compilar esto con un compilador de línea de comandos, compile IService1.cs y Service1.cs en una biblioteca de clase hace referencia a `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-168">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library referencing `System.ServiceModel.dll`.</span></span> <span data-ttu-id="2b5b5-169">Y compile Program.cs en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-169">And compile Program.cs to a console application.</span></span>  
  
```csharp
// IService1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
//Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
using GettingStartedLib;  
using System.ServiceModel.Description;   
  
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
'IService1.vb  
Imports System  
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
'Service1.vb  
Imports System  
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
'Module1.vb  
Imports System  
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
>  <span data-ttu-id="2b5b5-170">Servicios como este requieren permiso para registrar las direcciones HTTP en el equipo para la realización de escuchas.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-170">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="2b5b5-171">Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-171">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="2b5b5-172">Cómo configurar las reservas de espacio de nombres, consulte [configurar HTTP y HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="2b5b5-172"> how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="2b5b5-173">Al ejecutarse en [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], the service.exe se debe ejecutar con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-173">When running under [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], the service.exe must be run with administrator privileges.</span></span>  
  
 <span data-ttu-id="2b5b5-174">Ahora, el servicio se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="2b5b5-174">Now the service is running.</span></span> <span data-ttu-id="2b5b5-175">Continúe con [Cómo: crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="2b5b5-175">Proceed to [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="2b5b5-176">Para obtener información de solución de problemas, consulte [el Tutorial de introducción de la solución de problemas](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="2b5b5-176">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b5b5-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b5b5-177">See Also</span></span>  
 [<span data-ttu-id="2b5b5-178">Introducción</span><span class="sxs-lookup"><span data-stu-id="2b5b5-178">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="2b5b5-179">Autohospedaje</span><span class="sxs-lookup"><span data-stu-id="2b5b5-179">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
