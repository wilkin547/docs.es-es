---
title: 'Cómo: habilitar el seguimiento de WIF'
ms.date: 03/30/2017
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 17650e06cb505dd778a9c0980c2a32fda8099cb4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856249"
---
# <a name="how-to-enable-wif-tracing"></a><span data-ttu-id="7cbd8-102">Cómo: habilitar el seguimiento de WIF</span><span class="sxs-lookup"><span data-stu-id="7cbd8-102">How To: Enable WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="7cbd8-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="7cbd8-103">Applies To</span></span>  
  
-   <span data-ttu-id="7cbd8-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="7cbd8-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="7cbd8-105">Formularios Web Forms ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="7cbd8-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="7cbd8-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="7cbd8-106">Summary</span></span>  
 <span data-ttu-id="7cbd8-107">En este tema de procedimientos se proporcionan los procedimientos paso a paso detallados para habilitar el seguimiento de WIF en una aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-107">This How-To provides detailed step-by-step procedures for enabling WIF tracing in an ASP.NET application.</span></span> <span data-ttu-id="7cbd8-108">También se proporcionan instrucciones de prueba de la aplicación para comprobar que el registro y el agente de escucha de seguimiento funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-108">It also provides instructions testing the application to verify that the trace listener and log are working correctly.</span></span> <span data-ttu-id="7cbd8-109">Esta sección de procedimientos no tiene instrucciones detalladas para crear un servicio de token de seguridad (STS) y en su lugar se utiliza el STS de desarrollo que se incluye con la extensión Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="7cbd8-110">El STS de desarrollo no realiza la autenticación real y está pensado únicamente para pruebas.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="7cbd8-111">Para completar este procedimiento, tendrá que instalar la extensión Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="7cbd8-112">Se puede descargar en la siguiente ubicación: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849).</span><span class="sxs-lookup"><span data-stu-id="7cbd8-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7cbd8-113">Habilitar la traza de WIF para aplicaciones pasivas, es decir, aplicaciones que utilizan el protocolo de WS-Federation, podría exponer la aplicación a ataques de denegación de servicio (DoS) o a la divulgación de información a terceros malintencionados.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-113">Enabling WIF tracing for passive applications, that is, applications that use the WS-Federation protocol, can potentially expose the application to denial of service (DoS) attacks or to information disclosure to a malicious party.</span></span> <span data-ttu-id="7cbd8-114">Esto incluye tanto RP pasivos como STS pasivos.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-114">This includes both passive RPs and passive STSes.</span></span> <span data-ttu-id="7cbd8-115">Por este motivo, es recomendable que no habilite el seguimiento de WIF para RP o STS pasivos en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-115">For this reason, we recommend that you not enable WIF tracing for passive RPs or STSes in a production environment.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="7cbd8-116">Contenido</span><span class="sxs-lookup"><span data-stu-id="7cbd8-116">Contents</span></span>  
  
-   <span data-ttu-id="7cbd8-117">Objetivos</span><span class="sxs-lookup"><span data-stu-id="7cbd8-117">Objectives</span></span>  
  
-   <span data-ttu-id="7cbd8-118">Información general</span><span class="sxs-lookup"><span data-stu-id="7cbd8-118">Overview</span></span>  
  
-   <span data-ttu-id="7cbd8-119">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="7cbd8-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="7cbd8-120">Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar el seguimiento</span><span class="sxs-lookup"><span data-stu-id="7cbd8-120">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="7cbd8-121">Paso 2 – Probar la solución</span><span class="sxs-lookup"><span data-stu-id="7cbd8-121">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="7cbd8-122">Objetivos</span><span class="sxs-lookup"><span data-stu-id="7cbd8-122">Objectives</span></span>  
  
-   <span data-ttu-id="7cbd8-123">Crear una aplicación ASP.NET simple que use WIF y el STS de desarrollo desde la herramienta Identity and Access Tool</span><span class="sxs-lookup"><span data-stu-id="7cbd8-123">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="7cbd8-124">Habilitar el seguimiento y comprobar que funciona</span><span class="sxs-lookup"><span data-stu-id="7cbd8-124">Enable tracing and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="7cbd8-125">Información general</span><span class="sxs-lookup"><span data-stu-id="7cbd8-125">Overview</span></span>  
 <span data-ttu-id="7cbd8-126">El seguimiento permite depurar y solucionar muchos tipos de problemas con WIF, como tokens, cookies, notificaciones, mensajes de protocolo, etc.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-126">Tracing enables you to debug and troubleshoot many types of issues with WIF, including tokens, cookies, claims, protocol messages, and more.</span></span> <span data-ttu-id="7cbd8-127">El seguimiento de WIF es similar al seguimiento de WCF; por ejemplo, puede elegir el nivel de detalle de los seguimientos para mostrar cualquier tipo de mensaje, desde mensajes críticos a todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-127">WIF tracing is similar to WCF tracing; for example, you can choose the verbosity of traces to display everything from critical messages to all messages.</span></span> <span data-ttu-id="7cbd8-128">Los seguimientos de WIF se pueden generar en archivos **.xml** o en archivos **.svclog** que se pueden consultar mediante la herramienta Visor de seguimiento de servicios.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-128">WIF traces can be generated in **.xml** files or in **.svclog** files that are viewable by using the Service Trace Viewer Tool.</span></span> <span data-ttu-id="7cbd8-129">Esta herramienta se encuentra en el directorio **bin** de la ruta de instalación de Windows SDK del equipo, por ejemplo: **C:\Archivos de programa\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-129">This tool is located in the **bin** directory of the Windows SDK install path on your computer, for example: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="7cbd8-130">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="7cbd8-130">Summary of Steps</span></span>  
  
-   <span data-ttu-id="7cbd8-131">Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar el seguimiento</span><span class="sxs-lookup"><span data-stu-id="7cbd8-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="7cbd8-132">Paso 2 – Probar la solución</span><span class="sxs-lookup"><span data-stu-id="7cbd8-132">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a><span data-ttu-id="7cbd8-133">Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar el seguimiento</span><span class="sxs-lookup"><span data-stu-id="7cbd8-133">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
 <span data-ttu-id="7cbd8-134">En este paso, creará una aplicación de formularios Web Forms de ASP.NET y modificará el archivo *Web.config* para habilitar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-134">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable tracing.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="7cbd8-135">Para crear una aplicación de ASP.NET sencilla</span><span class="sxs-lookup"><span data-stu-id="7cbd8-135">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="7cbd8-136">Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-136">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="7cbd8-137">En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-137">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="7cbd8-138">En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-138">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="7cbd8-139">Haga clic con el botón derecho en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-139">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5.  <span data-ttu-id="7cbd8-140">Aparecerá la ventana **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-140">The **Identity and Access** window appears.</span></span> <span data-ttu-id="7cbd8-141">En **Proveedores**, seleccione **Test your application with the Local Development STS** (Probar la aplicación con el STS de desarrollo local) y haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-141">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6.  <span data-ttu-id="7cbd8-142">Cree una carpeta con el nombre **logs** en la raíz de la unidad **C:**, de la siguiente manera: **C:\logs**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-142">Create a new folder in named **logs** in the root of the **C:** drive, like shown: **C:\logs**</span></span>  
  
7.  <span data-ttu-id="7cbd8-143">Agregue el siguiente elemento **\<system.diagnostics>** al archivo de configuración *Web.config* inmediatamente después del elemento **\</configSections>** de cierre, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7cbd8-143">Add the following **\<system.diagnostics>** element to the *Web.config* configuration file immediately following the closing **\</configSections>** element, like shown:</span></span>  
  
    ```xml  
    <configuration>  
        <configSections>  
        …  
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="7cbd8-144">La ubicación del directorio especificado en el atributo **initializeData** debe existir antes de que pueda comenzar el registro.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-144">The directory location specified in the **initializeData** attribute must exist before logging can begin.</span></span> <span data-ttu-id="7cbd8-145">Si no existe la ubicación, no se creará ningún registro.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-145">If the location does not exist, no logs will be created.</span></span>  
  
     <span data-ttu-id="7cbd8-146">Las opciones de configuración anteriores habilitarán el seguimiento **Detallado** para WIF y guardarán el registro resultante en el archivo **C:\logs\WIF.xml**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-146">The configuration settings above will enable **Verbose** tracing for WIF and save the resulting log to the **C:logsWIF.xml** file.</span></span>  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="7cbd8-147">Paso 2 – Probar la solución</span><span class="sxs-lookup"><span data-stu-id="7cbd8-147">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="7cbd8-148">En este paso, probará la aplicación ASP.NET habilitada con WIF para comprobar que los registros se están grabando.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-148">In this step, you will test your WIF-enabled ASP.NET application to verify that logs are being recorded.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a><span data-ttu-id="7cbd8-149">Para probar la aplicación ASP.NET habilitada con WIF para un seguimiento correcto</span><span class="sxs-lookup"><span data-stu-id="7cbd8-149">To test your WIF-enabled ASP.NET application for successful tracing</span></span>  
  
1.  <span data-ttu-id="7cbd8-150">Presione la tecla **F5** para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-150">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="7cbd8-151">Debe aparecer la página principal de ASP.NET predeterminada y se le debe autenticar automáticamente con el nombre de usuario *Terry*, que es el usuario predeterminado devuelto por el STS de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-151">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2.  <span data-ttu-id="7cbd8-152">Cierre la ventana del explorador y después desplácese hasta la carpeta **C:\logs**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-152">Close the browser window and then navigate to the **C:\logs** folder.</span></span> <span data-ttu-id="7cbd8-153">Abra el archivo **C:\logs\WIF.xml** mediante un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-153">Open the **C:\logs\WIF.xml** file using a text editor.</span></span>  
  
3.  <span data-ttu-id="7cbd8-154">Inspeccione el archivo **WIF.xml** y compruebe que contiene entradas que comienzan por **\<E2ETraceEvent>**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-154">Inspect the **WIF.xml** file and verify that it contains entries starting with **\<E2ETraceEvent>**.</span></span> <span data-ttu-id="7cbd8-155">Estos seguimientos contendrán elementos **\<TraceRecord>** con descripciones de la actividad objeto de seguimiento, como **Validación de SecurityToken**.</span><span class="sxs-lookup"><span data-stu-id="7cbd8-155">These traces will contain **\<TraceRecord>** elements with descriptions for the traced activity, such as **Validating SecurityToken**.</span></span>
