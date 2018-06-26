---
title: Procedimiento para hospedar y ejecutar un servicio básico de Windows Communication Foundation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: f1c56ed83fa214cf781a833e05642635ac24b0c5
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753505"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="77fa3-102">Procedimiento para hospedar y ejecutar un servicio básico de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="77fa3-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>
<span data-ttu-id="77fa3-103">Esta es la tercera de las seis tareas necesarias para crear una aplicación de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="77fa3-103">This is the third of six tasks required to create a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="77fa3-104">Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="77fa3-105">En este tema se describe cómo hospedar un servicio de Windows Communication Foundation (WCF) en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="77fa3-105">This topic describes how to host a Windows Communication Foundation (WCF) service in a console application.</span></span> <span data-ttu-id="77fa3-106">Este procedimiento consta de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="77fa3-106">This procedure consists of the following steps:</span></span>  
  
-   <span data-ttu-id="77fa3-107">Cree un proyecto de aplicación de consola para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-107">Create a console application project to host the service.</span></span>  
  
-   <span data-ttu-id="77fa3-108">Crear un host del servicio para el servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-108">Create a service host for the service.</span></span>  
  
-   <span data-ttu-id="77fa3-109">Habilitar el intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="77fa3-109">Enable metadata exchange.</span></span>  
  
-   <span data-ttu-id="77fa3-110">Abrir el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-110">Open the service host.</span></span>  
  
 <span data-ttu-id="77fa3-111">En el ejemplo que se ofrece después del procedimiento, se proporciona una lista completa del código escrito en esta tarea.</span><span class="sxs-lookup"><span data-stu-id="77fa3-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="77fa3-112">Para crear una nueva aplicación de consola para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="77fa3-112">To create a new console application to host the service</span></span>  
  
1.  <span data-ttu-id="77fa3-113">Cree un proyecto de aplicación de consola haciendo clic con el botón derecho en la solución Introducción, y seleccionando **Agregar**, **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-113">Create a new Console Application project by right-clicking on the Getting Started solution, selecting, **Add**, **New Project**.</span></span> <span data-ttu-id="77fa3-114">En la parte izquierda del cuadro de diálogo **Agregar nuevo proyecto**, seleccione **Windows** en **C#** o **VB**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-114">In the **Add New Project** dialog on the left hand side of the dialog select **Windows** under **C#** or **VB**.</span></span> <span data-ttu-id="77fa3-115">En la sección central del cuadro de diálogo, seleccione **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-115">In the center section of the dialog select **Console Application**.</span></span> <span data-ttu-id="77fa3-116">Asigne al proyecto el nombre GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="77fa3-116">Name the project GettingStartedHost.</span></span>  
  
2.  <span data-ttu-id="77fa3-117">Establezca la plataforma de destino del proyecto GettingStartedHost en .NET Framework 4.5 haciendo clic con el botón derecho en **GettingStartedHost** en el Explorador de soluciones y seleccionando **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-117">Set the target framework of the GettingStartedHost project to .NET Framework 4.5 by right clicking on **GettingStartedHost** in the Solution Explorer and selecting **Properties**.</span></span> <span data-ttu-id="77fa3-118">En el cuadro desplegable **Plataforma de destino**, seleccione **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-118">In the dropdown box labeled **Target Framework** select **.NET Framework 4.5**.</span></span> <span data-ttu-id="77fa3-119">Establecer la plataforma de destino de un proyecto de VB es algo diferente; en el cuadro de diálogo de propiedades del proyecto GettingStartedHost, haga clic en la pestaña **Compilar** en el lado izquierdo de la pantalla y, después, haga clic en el botón **Opciones de compilación avanzadas** en la esquina izquierda inferior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="77fa3-119">Setting the target framework for a VB project is a little different, in the GettingStartedHost project properties dialog, click the **Compile** tab on the left-hand side of the screen, and then click the **Advanced Compile Options** button at the lower left-hand corner of the dialog.</span></span> <span data-ttu-id="77fa3-120">Después, seleccione **.NET Framework 4.5** en el cuadro desplegable con la etiqueta **Plataforma de destino**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-120">Then select **.NET Framework 4.5** in the dropdown box labeled **Target Framework**.</span></span>  
  
     <span data-ttu-id="77fa3-121">Establecer la plataforma de destino hará que [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] recargue la solución; haga clic en **Aceptar** cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="77fa3-121">Setting the target framework will cause [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] to reload the solution, press **OK** when prompted.</span></span>  
  
3.  <span data-ttu-id="77fa3-122">Agregue una referencia al proyecto GettingStartedLib al proyecto GettingStartedHost haciendo clic con el botón derecho en la carpeta **Referencias** bajo el proyecto GettingStartedHost en el Explorador de soluciones y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-122">Add a reference to the GettingStartedLib project to the GettingStartedHost project by right clicking on the **References** folder under the GettingStartedHost project in the solution explorer and select **Add Reference**.</span></span> <span data-ttu-id="77fa3-123">En el lado izquierdo del cuadro de diálogo **Agregar referencia**, seleccione **Solución** y seleccione GettingStartedLib en la sección central del cuadro de diálogo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-123">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog and select GettingStartedLib in the center section of the dialog and click **Add**.</span></span> <span data-ttu-id="77fa3-124">Esto hace que los tipos definidos en GettingStartedLib estén disponibles para el proyecto GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="77fa3-124">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>  
  
4.  <span data-ttu-id="77fa3-125">Agregue una referencia a System.ServiceModel al proyecto GettingStartedHost haciendo clic con el botón derecho en la carpeta **Referencia** bajo el proyecto GettingStartedHost en el Explorador de soluciones y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-125">Add a reference to System.ServiceModel to the GettingStartedHost project by right-clicking the **Reference** folder under the GettingStartedHost project in Solution Explorer and select **Add** Reference.</span></span> <span data-ttu-id="77fa3-126">En el lado izquierdo del cuadro de diálogo **Agregar referencia**, seleccione **Framework**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-126">In the **Add Reference** dialog select **Framework** on the left-hand side of the dialog.</span></span> <span data-ttu-id="77fa3-127">En el cuadro de texto Ensamblados de búsqueda, escriba `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="77fa3-127">In the Search Assemblies textbox, type in `System.ServiceModel`.</span></span> <span data-ttu-id="77fa3-128">En la sección central del cuadro de diálogo, seleccione **System.ServiceModel**, haga clic en el botón **Agregar** y después en el botón **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="77fa3-128">In the center section of the dialog select **System.ServiceModel**, click the **Add** button, and click the **Close** button.</span></span> <span data-ttu-id="77fa3-129">Guarde la solución haciendo clic en el botón Guardar todo debajo del menú principal.</span><span class="sxs-lookup"><span data-stu-id="77fa3-129">Save the solution by clicking the Save All button below the main menu.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="77fa3-130">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="77fa3-130">To host the service</span></span>  
  
-   <span data-ttu-id="77fa3-131">Abra el archivo Program.cs o Module.vb y escriba el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="77fa3-131">Open the Program.cs or Module.vb file and enter the following code:</span></span>  
  
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
  
    1.  <span data-ttu-id="77fa3-132">Paso 1 - Crea una instancia de la clase Uri para contener la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-132">Step 1 - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="77fa3-133">Los servicios se identifican mediante una dirección URL que contiene una dirección base y un URI opcional.</span><span class="sxs-lookup"><span data-stu-id="77fa3-133">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="77fa3-134">Se da formato a la dirección base como sigue: [transporte]://[nombre de equipo o dominio][:nº de puerto opcional]/[segmento opcional de URI]La dirección base para el servicio de calculadora usa el transporte HTTP, localhost, el puerto 8000 y el segmento de URI "GettingStarted".</span><span class="sxs-lookup"><span data-stu-id="77fa3-134">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>  
  
    2.  <span data-ttu-id="77fa3-135">Paso 2 - Crea una instancia de la clase <xref:System.ServiceModel.ServiceHost> para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-135">Step 2 – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="77fa3-136">El constructor toma dos parámetros: el tipo de la clase que implementa el contrato de servicio y la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-136">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>  
  
    3.  <span data-ttu-id="77fa3-137">Paso 3 - Crea una nueva instancia de <xref:System.ServiceModel.Description.ServiceEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="77fa3-137">Step 3 – Creates a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="77fa3-138">Un punto de conexión de servicio consta de una dirección, un enlace y un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-138">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="77fa3-139">Por tanto, el constructor <xref:System.ServiceModel.Description.ServiceEndpoint> toma el tipo de interfaz del contrato de servicio, un enlace y una dirección.</span><span class="sxs-lookup"><span data-stu-id="77fa3-139">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="77fa3-140">El contrato de servicio es `ICalculator`, que se define e implemente en el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-140">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="77fa3-141">El enlace usado en este ejemplo es <xref:System.ServiceModel.WSHttpBinding>, que es un enlace integrado que se emplea para conectarse a extremos que son conformes a las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="77fa3-141">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="77fa3-142">Para obtener más información sobre los enlaces de WCF, vea [Información general de enlaces de Windows Communication Foundation](../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-142">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="77fa3-143">La dirección se anexa a la dirección base para identificar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="77fa3-143">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="77fa3-144">La dirección especificada en este código es "CalculatorService", por lo que la dirección completa para el punto de conexión es `"http://localhost:8000/GettingStarted/CalculatorService"` Agregar un punto de conexión de servicio es opcional cuando se usa .NET Framework 4.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="77fa3-144">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"` Adding a service endpoint is optional when using .NET Framework 4.0 or later.</span></span> <span data-ttu-id="77fa3-145">En estas versiones, si no se agrega ningún punto de conexión en el código o en la configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementada por el servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-145">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="77fa3-146">Para obtener más información sobre los puntos de conexión predeterminados, vea [Especificación de una dirección de punto de conexión](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-146">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="77fa3-147">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-147">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="77fa3-148">Agregar un punto de conexión de servicio es opcional cuando se usa .NET Framework 4.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="77fa3-148">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="77fa3-149">En estas versiones, si no se agrega ningún punto de conexión en el código o en la configuración, WCF agrega un punto de conexión predeterminado para cada combinación de dirección base y contrato implementada por el servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-149">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="77fa3-150">Para obtener más información sobre los puntos de conexión predeterminados, vea [Especificación de una dirección de punto de conexión](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-150">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="77fa3-151">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-151">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
    4.  <span data-ttu-id="77fa3-152">Paso 4 - Habilita el intercambio de metadatos.</span><span class="sxs-lookup"><span data-stu-id="77fa3-152">Step 4 – Enable metadata exchange.</span></span> <span data-ttu-id="77fa3-153">Los clientes usarán intercambio de metadatos para generar los servidores proxy que se usarán para llamar a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="77fa3-153">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="77fa3-154">Para habilitar el intercambio de metadatos, cree una instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, establezca su propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true` y agregue el comportamiento a la colección <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` de la instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="77fa3-154">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>  
  
    5.  <span data-ttu-id="77fa3-155">Paso 5 - Abre <xref:System.ServiceModel.ServiceHost> para escuchar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="77fa3-155">Step 5 – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="77fa3-156">Observe que el código espera que el usuario presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="77fa3-156">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="77fa3-157">Si no lo hace, la aplicación se cerrará inmediatamente y el servicio se cerrará. Observe también que se usa un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="77fa3-157">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="77fa3-158">Una vez creada la instancia de <xref:System.ServiceModel.ServiceHost>, el resto del código se coloca en un bloque try/catch.</span><span class="sxs-lookup"><span data-stu-id="77fa3-158">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="77fa3-159">Para obtener más información sobre cómo detectar de forma segura las excepciones producidas por <xref:System.ServiceModel.ServiceHost>, vea [Evitar problemas mediante una declaración de instrucción](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-159">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span></span>  
  
### <a name="to-verify-the-service-is-working"></a><span data-ttu-id="77fa3-160">Para comprobar si el servicio funciona</span><span class="sxs-lookup"><span data-stu-id="77fa3-160">To verify the service is working</span></span>  
  
1.  <span data-ttu-id="77fa3-161">Ejecute la aplicación de consola GettingStartedHost desde [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77fa3-161">Run the GettingStartedHost console application from inside [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="77fa3-162">Al ejecutarse en [!INCLUDE[wv](../../../includes/wv-md.md)] y sistemas operativos posteriores, el servicio se debe ejecutar con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="77fa3-162">When running on [!INCLUDE[wv](../../../includes/wv-md.md)] and later operating systems, the service must be run with administrator privileges.</span></span> <span data-ttu-id="77fa3-163">Dado que Visual se ejecutó con privilegios de administrador, GettingStartedHost también se ejecuta con esos privilegios.</span><span class="sxs-lookup"><span data-stu-id="77fa3-163">Because Visual Studio was run with Administrator privileges, GettingStartedHost is also run with Administrator privileges.</span></span> <span data-ttu-id="77fa3-164">También puede iniciar un nuevo símbolo del sistema con privilegios de administrador y ejecutar service.exe desde allí.</span><span class="sxs-lookup"><span data-stu-id="77fa3-164">You can also start a new command prompt running it with Administrator privileges and run service.exe within it.</span></span>  
  
2.  <span data-ttu-id="77fa3-165">Abra Internet Explorer y busque la página de depuración del servicio en `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="77fa3-165">Open Internet Explorer and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77fa3-166">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77fa3-166">Example</span></span>  
 <span data-ttu-id="77fa3-167">El siguiente ejemplo incluye el contrato de servicios y la implementación de los pasos anteriores del tutorial y hospeda el servicio en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="77fa3-167">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>  
  
 <span data-ttu-id="77fa3-168">Para compilar esto con un compilador de la línea de comandos, compile IService1.cs y Service1.cs en una biblioteca de clases haciendo referencia a `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="77fa3-168">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library referencing `System.ServiceModel.dll`.</span></span> <span data-ttu-id="77fa3-169">Y compile Program.cs en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="77fa3-169">And compile Program.cs to a console application.</span></span>  
  
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
>  <span data-ttu-id="77fa3-170">Servicios como este requieren permiso para registrar las direcciones HTTP en el equipo para la realización de escuchas.</span><span class="sxs-lookup"><span data-stu-id="77fa3-170">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="77fa3-171">Las cuentas Administrador tienen este permiso, pero las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP.</span><span class="sxs-lookup"><span data-stu-id="77fa3-171">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="77fa3-172">Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-172">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="77fa3-173">Cuando se ejecuta en Visual Studio, service.exe se debe ejecutar con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="77fa3-173">When running under Visual Studio, the service.exe must be run with administrator privileges.</span></span>  
  
 <span data-ttu-id="77fa3-174">Ahora, el servicio se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="77fa3-174">Now the service is running.</span></span> <span data-ttu-id="77fa3-175">Continúe hasta [Creación de un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-175">Proceed to [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="77fa3-176">Para obtener información de solución de problemas, vea [Solución de problemas con el tutorial de introducción](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-176">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77fa3-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="77fa3-177">See Also</span></span>  
 [<span data-ttu-id="77fa3-178">Introducción</span><span class="sxs-lookup"><span data-stu-id="77fa3-178">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="77fa3-179">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="77fa3-179">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
