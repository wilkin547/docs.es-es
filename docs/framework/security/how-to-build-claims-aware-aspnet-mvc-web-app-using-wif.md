---
title: 'Cómo: crear aplicaciones web MVC de ASP.NET para notificaciones mediante WIF'
ms.date: 03/30/2017
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
author: BrucePerlerMS
ms.openlocfilehash: 4a003acbf4e182a0493368b586a3add229d8b526
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48036007"
---
# <a name="how-to-build-claims-aware-aspnet-mvc-web-application-using-wif"></a><span data-ttu-id="4b7ee-102">Cómo: crear aplicaciones web MVC de ASP.NET para notificaciones mediante WIF</span><span class="sxs-lookup"><span data-stu-id="4b7ee-102">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="4b7ee-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="4b7ee-103">Applies To</span></span>  
  
-   <span data-ttu-id="4b7ee-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="4b7ee-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="4b7ee-105">ASP.NET® MVC</span><span class="sxs-lookup"><span data-stu-id="4b7ee-105">ASP.NET® MVC</span></span>  
  
## <a name="summary"></a><span data-ttu-id="4b7ee-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="4b7ee-106">Summary</span></span>  
 <span data-ttu-id="4b7ee-107">Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación web de ASP.NET MVC para notificaciones.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET MVC web application.</span></span> <span data-ttu-id="4b7ee-108">También proporciona instrucciones sobre cómo probar la aplicación web sencilla de ASP.NET MVC para notificaciones para obtener una implementación correcta de la autenticación basada en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-108">It also provides instructions how to test the simple claims-aware ASP.NET MVC web application for successful implementation of claims-based authentication.</span></span> <span data-ttu-id="4b7ee-109">Este tema de procedimientos no tiene instrucciones detalladas para crear un Servicio de tokens de seguridad (STS) y presupone que ya ha configurado uno.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="4b7ee-110">Contenido</span><span class="sxs-lookup"><span data-stu-id="4b7ee-110">Contents</span></span>  
  
-   <span data-ttu-id="4b7ee-111">Objetivos</span><span class="sxs-lookup"><span data-stu-id="4b7ee-111">Objectives</span></span>  
  
-   <span data-ttu-id="4b7ee-112">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="4b7ee-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4b7ee-113">Paso 1: Crear una aplicación sencilla de ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="4b7ee-113">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="4b7ee-114">Paso 2: Configurar una aplicación de ASP.NET MVC para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4b7ee-114">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="4b7ee-115">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="4b7ee-115">Step 3 – Test Your Solution</span></span>  
  
-   <span data-ttu-id="4b7ee-116">Elementos relacionados</span><span class="sxs-lookup"><span data-stu-id="4b7ee-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="4b7ee-117">Objetivos</span><span class="sxs-lookup"><span data-stu-id="4b7ee-117">Objectives</span></span>  
  
-   <span data-ttu-id="4b7ee-118">Configurar una aplicación web de ASP.NET MVC para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4b7ee-118">Configure ASP.NET MVC web application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="4b7ee-119">Probar una aplicación web de ASP.NET MVC para notificaciones correcta</span><span class="sxs-lookup"><span data-stu-id="4b7ee-119">Test successful claims-aware ASP.NET MVC web application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="4b7ee-120">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="4b7ee-120">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4b7ee-121">Paso 1: Crear una aplicación sencilla de ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="4b7ee-121">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="4b7ee-122">Paso 2: Configurar una aplicación de ASP.NET MVC para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4b7ee-122">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="4b7ee-123">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="4b7ee-123">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-simple-aspnet-mvc-application"></a><span data-ttu-id="4b7ee-124">Paso 1: Crear una aplicación sencilla de ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="4b7ee-124">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
 <span data-ttu-id="4b7ee-125">En este paso se crea una aplicación de ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-125">In this step, you will create a new ASP.NET MVC application.</span></span>  
  
#### <a name="to-create-simple-aspnet-mvc-application"></a><span data-ttu-id="4b7ee-126">Para crear una aplicación sencilla de ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="4b7ee-126">To create simple ASP.NET MVC application</span></span>  
  
1.  <span data-ttu-id="4b7ee-127">Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-127">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="4b7ee-128">En la ventana **Nuevo proyecto**, haga clic en **Aplicación web de ASP.NET MVC 3**.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-128">In the **New Project** window, click **ASP.NET MVC 3 Web Application**.</span></span>  
  
3.  <span data-ttu-id="4b7ee-129">En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-129">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="4b7ee-130">En el cuadro de diálogo **Nuevo proyecto de ASP.NET MVC 3**, seleccione **Aplicación de Internet** de las plantillas disponibles; asegúrese de que **Motor de vista** se establece en **Razor** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-130">In the **New ASP.NET MVC 3 Project** dialog, select **Internet Application** from the available templates, ensure **View Engine** is set to **Razor**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="4b7ee-131">Cuando se abre el nuevo proyecto, haga clic con el botón derecho en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione la opción **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-131">When the new project opens, right-click the **TestApp** project in **Solution Explorer** and select the **Properties** option.</span></span>  
  
6.  <span data-ttu-id="4b7ee-132">En la página de propiedades del proyecto, haga clic en la pestaña **Web** situada a la izquierda y asegúrese de que la opción **Usar servidor web de IIS local** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-132">On the project’s properties page, click on the **Web** tab on the left and ensure that the **Use Local IIS Web Server** option is selected.</span></span>  
  
## <a name="step-2--configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="4b7ee-133">Paso 2: Configurar una aplicación de ASP.NET MVC para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4b7ee-133">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="4b7ee-134">En este paso agregará entradas de configuración al archivo de configuración *Web.config* de su aplicación web de ASP.NET MVC para notificaciones.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-134">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET MVC web application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="4b7ee-135">Para configurar una aplicación de ASP.NET MVC para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4b7ee-135">To configure ASP.NET MVC application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="4b7ee-136">Agregue las siguientes definiciones de la sección de configuración al archivo de configuración *Web.config*.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-136">Add the following configuration section definitions to the *Web.config* configuration file.</span></span> <span data-ttu-id="4b7ee-137">Estas definen las secciones de configuración necesarias para Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-137">These define configuration sections required by Windows Identity Foundation.</span></span> <span data-ttu-id="4b7ee-138">Agregue las definiciones inmediatamente después del elemento de apertura **\<configuration>**:</span><span class="sxs-lookup"><span data-stu-id="4b7ee-138">Add the definitions immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  <span data-ttu-id="4b7ee-139">Agregue un elemento **\<location>** que permita el acceso a los metadatos de federación de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="4b7ee-139">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3.  <span data-ttu-id="4b7ee-140">Agregue las siguientes entradas de configuración dentro de los elementos **\<system.web>** para denegar usuarios, deshabilitar la autenticación nativa y habilitar WIF para administrar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-140">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  <span data-ttu-id="4b7ee-141">Agregue las siguientes entradas de configuración relacionadas con Windows Identity Foundation y asegúrese de que su URL de la aplicación ASP.NET y el número de puerto coinciden con los valores de la entrada **\<audienceUris>**, el atributo **realm** del elemento **\<wsFederation>** y el atributo **reply** del elemento **\<wsFederation>**.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-141">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="4b7ee-142">También asegúrese de que el valor **issuer** se adapta a su URL del servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="4b7ee-142">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="false" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="false" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
5.  <span data-ttu-id="4b7ee-143">Agregue una referencia al ensamblado <xref:System.IdentityModel>.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-143">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
6.  <span data-ttu-id="4b7ee-144">Compile la solución y asegúrese de que existan errores.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-144">Compile the solution to make sure there are errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="4b7ee-145">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="4b7ee-145">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="4b7ee-146">En este paso probará la aplicación web de ASP.NET MVC configurada para la autenticación basada en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-146">In this step you will test your ASP.NET MVC web application configured for claims-based authentication.</span></span> <span data-ttu-id="4b7ee-147">Para realizar una prueba básica, agregará código simple que muestra notificaciones en el token emitido mediante el servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="4b7ee-147">To perform basic test you will add simple code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="4b7ee-148">Para probar su aplicación de ASP.NET MVC para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4b7ee-148">To test your ASP.NET MVC application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="4b7ee-149">En el **Explorador de soluciones**, expanda la carpeta **Controladores** y abra el archivo *HomeController.cs* en el editor.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-149">In the **Solution Explorer**, expand the **Controllers** folder and open *HomeController.cs* file in the editor.</span></span> <span data-ttu-id="4b7ee-150">Agregue el código siguiente al método **Index**:</span><span class="sxs-lookup"><span data-stu-id="4b7ee-150">Add the following code to the **Index** method:</span></span>  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
    ```  
  
2.  <span data-ttu-id="4b7ee-151">En el **Explorador de soluciones**, expanda **Vistas** y, después, las carpetas **Inicio**, y abra el archivo *Index.cshtml* en el editor.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-151">In the **Solution Explorer** expand **Views** and then **Home** folders and open *Index.cshtml* file in the editor.</span></span> <span data-ttu-id="4b7ee-152">Elimine su contenido y agregue el siguiente marcado:</span><span class="sxs-lookup"><span data-stu-id="4b7ee-152">Delete its contents and add the following markup:</span></span>  
  
    ```html  
    @{  
        ViewBag.Title = "Home Page";  
    }  
  
    <h2>Welcome: @ViewBag.ClaimsIdentity.Name</h2>  
    <h3>Values from Identity</h3>  
    <table>  
        <tr>  
            <th>  
                IsAuthenticated   
            </th>  
            <td>  
                @ViewBag.ClaimsIdentity.IsAuthenticated   
            </td>  
        </tr>  
        <tr>  
            <th>  
                Name   
            </th>          
            <td>  
                @ViewBag.ClaimsIdentity.Name  
            </td>          
        </tr>  
    </table>  
    <h3>Claims from ClaimsIdentity</h3>  
    <table>  
        <tr>  
            <th>  
                Claim Type  
            </th>  
            <th>  
                Claim Value  
            </th>  
            <th>  
                Value Type  
            </th>  
            <th>  
                Subject Name  
            </th>          
            <th>  
                Issuer Name  
            </th>          
        </tr>  
            @foreach (System.Security.Claims.Claim claim in ViewBag.ClaimsIdentity.Claims ) {  
        <tr>  
            <td>  
                @claim.Type  
            </td>  
            <td>  
                @claim.Value  
            </td>  
            <td>  
                @claim.ValueType  
            </td>  
            <td>  
                @claim.Subject.Name  
            </td>  
            <td>  
                @claim.Issuer  
            </td>  
        </tr>  
    }  
    </table>  
    ```  
  
3.  <span data-ttu-id="4b7ee-153">Presione la tecla **F5** para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-153">Run the solution by pressing the **F5** key.</span></span>  
  
4.  <span data-ttu-id="4b7ee-154">Debe estar presente en la página que muestra las notificaciones del token que ha emitido mediante el servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4b7ee-154">You should be presented with the page that displays the claims in the token that was issued to you by Security Token Service.</span></span>  
  
## <a name="related-items"></a><span data-ttu-id="4b7ee-155">Elementos relacionados</span><span class="sxs-lookup"><span data-stu-id="4b7ee-155">Related Items</span></span>  
  
-   [<span data-ttu-id="4b7ee-156">Crear aplicaciones de formularios Web de ASP.NET para notificaciones mediante WIF</span><span class="sxs-lookup"><span data-stu-id="4b7ee-156">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)
