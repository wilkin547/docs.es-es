---
title: Cómo habilitar WIF para una aplicación de servicio web WCF
ms.date: 03/30/2017
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
author: BrucePerlerMS
ms.openlocfilehash: 6af0336e19df4ba2a99a52f8726e78ed92f5a79e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323309"
---
# <a name="how-to-enable-wif-for-a-wcf-web-service-application"></a><span data-ttu-id="5606d-102">Cómo habilitar WIF para una aplicación de servicio web WCF</span><span class="sxs-lookup"><span data-stu-id="5606d-102">How To: Enable WIF for a WCF Web Service Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="5606d-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="5606d-103">Applies To</span></span>  
  
-   <span data-ttu-id="5606d-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="5606d-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="5606d-105">Microsoft® Windows® Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="5606d-105">Microsoft® Windows® Communication Foundation (WCF)</span></span>  
  
## <a name="summary"></a><span data-ttu-id="5606d-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="5606d-106">Summary</span></span>  
 <span data-ttu-id="5606d-107">En este tema de procedimientos se proporcionan los procedimientos paso a paso detallados para habilitar WIF en un servicio Web de WCF.</span><span class="sxs-lookup"><span data-stu-id="5606d-107">This How-To provides detailed step-by-step procedures for enabling WIF in a WCF web service.</span></span> <span data-ttu-id="5606d-108">También se proporcionan instrucciones sobre cómo probar la aplicación para comprobar que el servicio Web está presentando notificaciones correctamente cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5606d-108">It also provides instructions for how to test the application to verify that the web service is correctly presenting claims when the application is run.</span></span> <span data-ttu-id="5606d-109">Esta sección de procedimientos no tiene instrucciones detalladas para crear un servicio de token de seguridad (STS) y en su lugar se utiliza el STS de desarrollo que se incluye con la extensión Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="5606d-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="5606d-110">El STS de desarrollo no realiza la autenticación real y está pensado únicamente para pruebas.</span><span class="sxs-lookup"><span data-stu-id="5606d-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="5606d-111">Para completar este procedimiento, tendrá que instalar la extensión Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="5606d-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="5606d-112">Se puede descargar desde la ubicación siguiente: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="5606d-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="5606d-113">Contenido</span><span class="sxs-lookup"><span data-stu-id="5606d-113">Contents</span></span>  
  
-   <span data-ttu-id="5606d-114">Objetivos</span><span class="sxs-lookup"><span data-stu-id="5606d-114">Objectives</span></span>  
  
-   <span data-ttu-id="5606d-115">Información general</span><span class="sxs-lookup"><span data-stu-id="5606d-115">Overview</span></span>  
  
-   <span data-ttu-id="5606d-116">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="5606d-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="5606d-117">Paso 1 – Crear un servicio WCF simple</span><span class="sxs-lookup"><span data-stu-id="5606d-117">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="5606d-118">Paso 2 – Crear una aplicación cliente para el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="5606d-118">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="5606d-119">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="5606d-119">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="5606d-120">Objetivos</span><span class="sxs-lookup"><span data-stu-id="5606d-120">Objectives</span></span>  
  
-   <span data-ttu-id="5606d-121">Crear un servicio WCF que requiera tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="5606d-121">Create a WCF service that requires issued tokens</span></span>  
  
-   <span data-ttu-id="5606d-122">Crear un cliente WCF que solicite un token de un STS y lo pase al servicio WCF</span><span class="sxs-lookup"><span data-stu-id="5606d-122">Create a WCF client that requests a token from an STS and passes it to the WCF service</span></span>  
  
## <a name="overview"></a><span data-ttu-id="5606d-123">Información general</span><span class="sxs-lookup"><span data-stu-id="5606d-123">Overview</span></span>  
 <span data-ttu-id="5606d-124">El objetivo de este tema de procedimientos es demostrar la manera en que un desarrollador puede utilizar la autenticación federada cuando desarrolle servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="5606d-124">This How-To is intended to demonstrate how a developer can use federated authentication when developing WCF services.</span></span> <span data-ttu-id="5606d-125">Entre las ventajas del uso de la federación en servicios WCF se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="5606d-125">Some of the benefits of using federation in WCF services include:</span></span>  
  
1. <span data-ttu-id="5606d-126">La factorización de la lógica de autenticación fuera del código de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="5606d-126">Factoring authentication logic out of WCF service code</span></span>  
  
2. <span data-ttu-id="5606d-127">La reutilización de las soluciones de administración de identidades existentes</span><span class="sxs-lookup"><span data-stu-id="5606d-127">Re-using existing identity management solutions</span></span>  
  
3. <span data-ttu-id="5606d-128">Interoperabilidad con otras soluciones de identidad</span><span class="sxs-lookup"><span data-stu-id="5606d-128">Interoperability with other identity solutions</span></span>  
  
4. <span data-ttu-id="5606d-129">Flexibilidad y resistencia a cambios futuros</span><span class="sxs-lookup"><span data-stu-id="5606d-129">Flexibility and resilience to future changes</span></span>  
  
 <span data-ttu-id="5606d-130">WIF con la extensión Identity and Access Tool asociada facilitan el desarrollo y las pruebas de un servicio WCF mediante autenticación federada, como muestran los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="5606d-130">WIF and the associated Identity and Access tool make it easier to develop and test a WCF service using federated authentication, as the following steps demonstrate.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="5606d-131">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="5606d-131">Summary of Steps</span></span>  
  
-   <span data-ttu-id="5606d-132">Paso 1 – Crear un servicio WCF simple</span><span class="sxs-lookup"><span data-stu-id="5606d-132">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="5606d-133">Paso 2 – Crear una aplicación cliente para el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="5606d-133">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="5606d-134">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="5606d-134">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-wcf-service"></a><span data-ttu-id="5606d-135">Paso 1 – Crear un servicio WCF simple</span><span class="sxs-lookup"><span data-stu-id="5606d-135">Step 1 – Create a Simple WCF Service</span></span>  
 <span data-ttu-id="5606d-136">En este paso, creará un nuevo servicio WCF que utilice el STS de desarrollo que se incluye con la herramienta Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="5606d-136">In this step, you will create a new WCF service that uses the Development STS that is included with the Identity and Access tool.</span></span>  
  
#### <a name="to-create-a-simple-wcf-service"></a><span data-ttu-id="5606d-137">Para crear un servicio WCF simple</span><span class="sxs-lookup"><span data-stu-id="5606d-137">To create a simple WCF service</span></span>  
  
1. <span data-ttu-id="5606d-138">Inicie Visual Studio como administrador con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="5606d-138">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2. <span data-ttu-id="5606d-139">En Visual Studio, haga clic en **Archivo**, en **Nuevo** y, después, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="5606d-139">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="5606d-140">En la ventana **Nuevo proyecto**, haga clic en **Aplicación de servicios WCF**.</span><span class="sxs-lookup"><span data-stu-id="5606d-140">In the **New Project** window, click **WCF Service Application**.</span></span>  
  
4. <span data-ttu-id="5606d-141">En **Nombre**, escriba `TestService` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5606d-141">In **Name**, enter `TestService` and press **OK**.</span></span>  
  
5. <span data-ttu-id="5606d-142">Haga clic con el botón derecho en el proyecto **TestService** en el **Explorador de soluciones** y seleccione **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="5606d-142">Right-click the **TestService** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6. <span data-ttu-id="5606d-143">Aparecerá la ventana **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="5606d-143">The **Identity and Access** window appears.</span></span> <span data-ttu-id="5606d-144">En **Proveedores**, seleccione **Test your application with the Local Development STS** (Probar la aplicación con el STS de desarrollo local) y haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="5606d-144">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span> <span data-ttu-id="5606d-145">Identity and Access Tool configura el servicio para que use WIF y externalice la autenticación al STS de desarrollo local (**LocalSTS**), para lo que agrega elementos de configuración al archivo *web.config*.</span><span class="sxs-lookup"><span data-stu-id="5606d-145">The Identity and Access Tool configures the service to use WIF and to outsource authentication to the local development STS (**LocalSTS**) by adding configuration elements to the *Web.config* file.</span></span>  
  
7. <span data-ttu-id="5606d-146">En el archivo *Service1.svc.cs*, agregue una directiva `using` para el espacio de nombres **System.Security.Claims** y reemplace el código existente por lo siguiente. Después, guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="5606d-146">In the *Service1.svc.cs* file, add a `using` directive for the **System.Security.Claims** namespace and replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     <span data-ttu-id="5606d-147">El método `ComputeResponse` muestra las propiedades de las distintas notificaciones emitidas por **LocalSTS**.</span><span class="sxs-lookup"><span data-stu-id="5606d-147">The `ComputeResponse` method displays the properties of various claims that are issued by **LocalSTS**.</span></span>  
  
8. <span data-ttu-id="5606d-148">En el archivo *IService1.cs*, reemplace el código existente por lo siguiente. Después, guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="5606d-148">In the *IService1.cs* file, replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. <span data-ttu-id="5606d-149">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5606d-149">Build the project.</span></span>  
  
10. <span data-ttu-id="5606d-150">Presione **Ctrl+F5** para ejecutar el servicio sin iniciar el depurador.</span><span class="sxs-lookup"><span data-stu-id="5606d-150">Press **Ctrl-F5** to run the service without starting the debugger.</span></span> <span data-ttu-id="5606d-151">Se debería abrir una página web para el servicio. Para comprobar que **LocalSTS** se está ejecutando, examine el área de notificaciones (la bandeja del sistema).</span><span class="sxs-lookup"><span data-stu-id="5606d-151">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5606d-152">**TestService** y **LocalSTS** deben estar en ejecución cuando se agrega una referencia de servicio a la aplicación cliente en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="5606d-152">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client application in the next step.</span></span>  
  
## <a name="step-2--create-a-client-application-for-the-wcf-service"></a><span data-ttu-id="5606d-153">Paso 2 – Crear una aplicación cliente para el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="5606d-153">Step 2 – Create a Client Application for the WCF Service</span></span>  
 <span data-ttu-id="5606d-154">En este paso creará una aplicación de consola que utiliza el STS de desarrollo para autenticarse con el servicio WCF que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="5606d-154">In this step, you will create a console application that uses the Development STS to authenticate with the WCF service you created in the previous step.</span></span>  
  
#### <a name="to-create-a-client-application"></a><span data-ttu-id="5606d-155">Para crear una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="5606d-155">To create a client application</span></span>  
  
1. <span data-ttu-id="5606d-156">En Visual Studio, haga clic con el botón derecho en la solución, haga clic en **Agregar** y, después, en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="5606d-156">In Visual Studio, right-click on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2. <span data-ttu-id="5606d-157">En la ventana **Agregar nuevo proyecto**, seleccione **Aplicación de consola** en la lista de plantillas de **Visual C#**, escriba `Client` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5606d-157">In the **Add New Project** window, select **Console Application** from the **Visual C#** templates list, enter `Client`, and then press **OK**.</span></span> <span data-ttu-id="5606d-158">El nuevo proyecto se creará en la carpeta de la solución.</span><span class="sxs-lookup"><span data-stu-id="5606d-158">The new project will be created in your solution folder.</span></span>  
  
3. <span data-ttu-id="5606d-159">Haga clic con el botón derecho en **Referencias** debajo del proyecto **Cliente** y, después, haga clic en **Agregar referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="5606d-159">Right-click on **References** under the **Client** project, and then click **Add Service Reference**.</span></span>  
  
4. <span data-ttu-id="5606d-160">En la ventana **Agregar referencia de servicio**, haga clic en la flecha desplegable del botón **Detectar** y en **Servicios de la solución**.</span><span class="sxs-lookup"><span data-stu-id="5606d-160">In the **Add Service Reference** window, click the drop-down arrow on the **Discover** button and click **Services in Solution**.</span></span> <span data-ttu-id="5606d-161">La **Dirección** se rellenará automáticamente con el servicio WCF que ha creado anteriormente y el **Espacio de nombres** se establecerá en **ServiceReference1**.</span><span class="sxs-lookup"><span data-stu-id="5606d-161">The **Address** will automatically populate with the WCF service you created earlier, and the **Namespace** will be set to **ServiceReference1**.</span></span> <span data-ttu-id="5606d-162">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5606d-162">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5606d-163">**TestService** y **LocalSTS** deben estar en ejecución cuando se agregue la referencia de servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="5606d-163">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client.</span></span>  
  
5. <span data-ttu-id="5606d-164">Visual Studio generará clases de proxy para el servicio WCF y agregará toda la información de referencia necesaria.</span><span class="sxs-lookup"><span data-stu-id="5606d-164">Visual Studio will generate proxy classes for the WCF service, and add all of the necessary reference information.</span></span> <span data-ttu-id="5606d-165">También agregará elementos al archivo *App.config* para configurar el cliente para que obtenga un token del STS a fin de autenticarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="5606d-165">It will also add elements to the *App.config* file to configure the client to get a token from the STS to authenticate with the service.</span></span> <span data-ttu-id="5606d-166">Cuando este proceso haya acabado, se abrirá el archivo **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="5606d-166">When this process is finished, the **Program.cs** file will open.</span></span> <span data-ttu-id="5606d-167">Agregue una directiva `using` para **System.ServiceModel** y otra para **Client.ServiceReference1**, reemplace el método **Principal** con el código siguiente y, después, guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="5606d-167">Add a `using` directive for **System.ServiceModel** and another for **Client.ServiceReference1**, replace the **Main** method with the following code, then save the file:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6. <span data-ttu-id="5606d-168">Abra el archivo *App.config* y agregue el siguiente código XML como primer elemento secundario bajo el elemento `<system.serviceModel>`; después, guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="5606d-168">Open the *App.config* file and add the following XML as the first child element under the `<system.serviceModel>` element, then save the file:</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
    ```  
  
     <span data-ttu-id="5606d-169">Esto deshabilita la validación de certificados.</span><span class="sxs-lookup"><span data-stu-id="5606d-169">This disables certificate validation.</span></span>  
  
7. <span data-ttu-id="5606d-170">Haga clic con el botón derecho en la solución **TestService** y haga clic en **Establecer proyectos de inicio**.</span><span class="sxs-lookup"><span data-stu-id="5606d-170">Right-click the **TestService** solution and click on **Set StartUp Projects**.</span></span> <span data-ttu-id="5606d-171">Se abre la página de propiedades **Proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="5606d-171">The **Startup Project** property page opens.</span></span> <span data-ttu-id="5606d-172">En la página de propiedades **Proyecto de inicio**, seleccione **Varios proyectos de inicio** y, después, haga clic en el campo **Acción** para cada proyecto y seleccione **Iniciar** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="5606d-172">In the **Startup Project** property page, select **Multiple startup projects** then click in the **Action** field for each project and select **Start** from the drop-down menu.</span></span> <span data-ttu-id="5606d-173">Haga clic en **Aceptar** para guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="5606d-173">Click **OK** to save the settings.</span></span>  
  
8. <span data-ttu-id="5606d-174">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="5606d-174">Build the solution.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="5606d-175">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="5606d-175">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="5606d-176">En este paso probará la aplicación WCF habilitada para WIF y comprobará que se presentan las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="5606d-176">In this step you will test your WIF-enabled WCF application and verify that claims are presented.</span></span>  
  
#### <a name="to-test-your-wif-enabled-wcf-application-for-claims"></a><span data-ttu-id="5606d-177">Para probar la aplicación WCF habilitada para WIF para las notificaciones</span><span class="sxs-lookup"><span data-stu-id="5606d-177">To test your WIF-enabled WCF application for claims</span></span>  
  
1. <span data-ttu-id="5606d-178">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5606d-178">Press **F5** to build and run the application.</span></span> <span data-ttu-id="5606d-179">Debe estar presente en una ventana de consola y el texto siguiente: **Presione la tecla ENTRAR para invocar el servicio, cualquier otra tecla para salir de la aplicación:**</span><span class="sxs-lookup"><span data-stu-id="5606d-179">You should be presented with a console window, and the following text: **Press Enter key to invoke service, any other key to quit application:**</span></span>  
  
2. <span data-ttu-id="5606d-180">Presione **ENTRAR**; en la consola debería aparecer la siguiente información de las notificaciones:</span><span class="sxs-lookup"><span data-stu-id="5606d-180">Press **Enter**, and the following claims information should appear in the console:</span></span>  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5606d-181">**TestService** y **LocalSTS** deben estar en ejecución antes de presionar **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="5606d-181">Both **TestService** and **LocalSTS** must be running before you press **Enter**.</span></span> <span data-ttu-id="5606d-182">Se debería abrir una página web para el servicio. Para comprobar que **LocalSTS** se está ejecutando, examine el área de notificaciones (la bandeja del sistema).</span><span class="sxs-lookup"><span data-stu-id="5606d-182">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
3. <span data-ttu-id="5606d-183">Si estas notificaciones aparecen en la consola, ha autenticado correctamente con el STS para mostrar notificaciones desde el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="5606d-183">If these claims appear in the console, you have successfully authenticated with the STS to display claims from the WCF service.</span></span>
