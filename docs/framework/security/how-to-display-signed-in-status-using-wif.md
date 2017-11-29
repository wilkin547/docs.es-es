---
title: "Cómo mostrar el estado “Firmado” mediante WIF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 494e67b39187a2a38f29f994e17051430d90f708
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-signed-in-status-using-wif"></a><span data-ttu-id="68c55-102">Cómo mostrar el estado “Firmado” mediante WIF</span><span class="sxs-lookup"><span data-stu-id="68c55-102">How To: Display Signed In Status Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="68c55-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="68c55-103">Applies To</span></span>  
  
-   <span data-ttu-id="68c55-104">Microsoft® Windows® Identity Foundation (WIF) 4.5</span><span class="sxs-lookup"><span data-stu-id="68c55-104">Microsoft® Windows® Identity Foundation (WIF) 4.5</span></span>  
  
-   <span data-ttu-id="68c55-105">Formularios Web Forms ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="68c55-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="68c55-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="68c55-106">Summary</span></span>  
 <span data-ttu-id="68c55-107">En este tema se describe cómo mostrar el estado de inicio de sesión en una aplicación ASP.NET habilitada para WIF.</span><span class="sxs-lookup"><span data-stu-id="68c55-107">This topic describes how to display the sign in status in a WIF-enabled ASP.NET application.</span></span> <span data-ttu-id="68c55-108">WIF proporciona el mecanismo para que la aplicación reconozca las notificaciones y administre la autenticación y la autorización de los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="68c55-108">WIF provides the mechanism for making your application claims-aware, and managing authentication and authorization for application resources.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="68c55-109">Contenido</span><span class="sxs-lookup"><span data-stu-id="68c55-109">Contents</span></span>  
  
-   <span data-ttu-id="68c55-110">Información general</span><span class="sxs-lookup"><span data-stu-id="68c55-110">Overview</span></span>  
  
-   <span data-ttu-id="68c55-111">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="68c55-111">Summary of Steps</span></span>  
  
-   <span data-ttu-id="68c55-112">Paso 1 - Instalar la extensión Identity and Access</span><span class="sxs-lookup"><span data-stu-id="68c55-112">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="68c55-113">Paso 2 - Crear una aplicación ASP.NET de usuario de confianza</span><span class="sxs-lookup"><span data-stu-id="68c55-113">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="68c55-114">Paso 3 - Habilitar STS de desarrollo local para autenticar usuarios</span><span class="sxs-lookup"><span data-stu-id="68c55-114">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="68c55-115">Paso 4 - Modificar la aplicación ASP.NET para que muestre el estado de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="68c55-115">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="68c55-116">Paso 5 - Probar la integración entre WIF y la aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68c55-116">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="overview"></a><span data-ttu-id="68c55-117">Información general</span><span class="sxs-lookup"><span data-stu-id="68c55-117">Overview</span></span>  
 <span data-ttu-id="68c55-118">En este tema se muestra cómo crear una aplicación sencilla que reconozca notificaciones mediante WIF y la manera de determinar con facilidad si un usuario ha iniciado sesión o no.</span><span class="sxs-lookup"><span data-stu-id="68c55-118">This topic demonstrates how to create a simple claims-aware application using WIF and how to easily display whether a user is signed in or not.</span></span> <span data-ttu-id="68c55-119">Los pasos siguientes utilizan el STS de desarrollo local que se incluye con la extensión de Visual Studio Identity and Access.</span><span class="sxs-lookup"><span data-stu-id="68c55-119">The following steps use the Local Development STS that is included with the Identity and Access Visual Studio Extension.</span></span> <span data-ttu-id="68c55-120">El STS de desarrollo local está pensado para que un entorno de desarrollo y pruebas proporcione un método sencillo para integrar notificaciones en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="68c55-120">The Local Development STS is intended for a testing and development environment to provide a simple method of integrating claims into your application.</span></span> <span data-ttu-id="68c55-121">Nunca se debe usar en un entorno de producción, ya que no realiza la autenticación real y no se requieren credenciales.</span><span class="sxs-lookup"><span data-stu-id="68c55-121">It should never be used in a production environment, as it does not perform real authentication and credentials are not required.</span></span> <span data-ttu-id="68c55-122">Sin embargo, el código imperativo de los pasos siguientes es el mismo para una aplicación lista para producción que usa autenticación real.</span><span class="sxs-lookup"><span data-stu-id="68c55-122">However, the imperative code in the following steps is the same for a production-ready application using real authentication.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="68c55-123">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="68c55-123">Summary of Steps</span></span>  
  
-   <span data-ttu-id="68c55-124">Paso 1 - Instalar la extensión Identity and Access</span><span class="sxs-lookup"><span data-stu-id="68c55-124">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="68c55-125">Paso 2 - Crear una aplicación ASP.NET de usuario de confianza</span><span class="sxs-lookup"><span data-stu-id="68c55-125">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="68c55-126">Paso 3 - Habilitar STS de desarrollo local para autenticar usuarios</span><span class="sxs-lookup"><span data-stu-id="68c55-126">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="68c55-127">Paso 4 - Modificar la aplicación ASP.NET para que muestre el estado de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="68c55-127">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="68c55-128">Paso 5 - Probar la integración entre WIF y la aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68c55-128">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="step-1--install-the-identity-and-access-extension"></a><span data-ttu-id="68c55-129">Paso 1 - Instalar la extensión Identity and Access</span><span class="sxs-lookup"><span data-stu-id="68c55-129">Step 1 – Install the Identity and Access Extension</span></span>  
 <span data-ttu-id="68c55-130">Este paso describe la manera de configurar la extensión Identity and Access en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="68c55-130">This step describes how to configure the Identity and Access extension to Visual Studio 2012.</span></span> <span data-ttu-id="68c55-131">Esta extensión automatiza el proceso de configuración de la aplicación para comunicarse con los extremos de STS.</span><span class="sxs-lookup"><span data-stu-id="68c55-131">This extension automates the process of configuring your application to communicate with STS endpoints.</span></span>  
  
#### <a name="to-install-the-identity-and-access-extension"></a><span data-ttu-id="68c55-132">Para instalar la extensión Identity and Access</span><span class="sxs-lookup"><span data-stu-id="68c55-132">To install the Identity and Access extension</span></span>  
  
1.  <span data-ttu-id="68c55-133">Inicie Visual Studio como administrador con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="68c55-133">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="68c55-134">En Visual Studio, haga clic en **Herramientas** y en **Administrador de extensiones**.</span><span class="sxs-lookup"><span data-stu-id="68c55-134">In Visual Studio, click **Tools** and click **Extension Manager**.</span></span> <span data-ttu-id="68c55-135">Aparece la ventana **Administrador de extensiones**.</span><span class="sxs-lookup"><span data-stu-id="68c55-135">The **Extension Manager** window appears.</span></span>  
  
3.  <span data-ttu-id="68c55-136">En el **Administrador de extensiones**, haga clic en **Extensiones en línea** en el menú izquierdo y, después, seleccione **Galería de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="68c55-136">In **Extension Manager**, click **Online Extensions** from the left menu, then select **Visual Studio Gallery**.</span></span>  
  
4.  <span data-ttu-id="68c55-137">En la esquina superior derecha del **Administrador de extensiones**, busque *Identity and Access*.</span><span class="sxs-lookup"><span data-stu-id="68c55-137">In the top right corner of **Extension Manager**, search for *Identity and Access*.</span></span>  
  
5.  <span data-ttu-id="68c55-138">El elemento **Identity and Access** aparecerá en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="68c55-138">The **Identity and Access** item will appear in the search results.</span></span> <span data-ttu-id="68c55-139">Haga clic en él y, después, en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="68c55-139">Click it, and then click **Download**.</span></span>  
  
6.  <span data-ttu-id="68c55-140">Aparece el cuadro de diálogo **Descargar e instalar**.</span><span class="sxs-lookup"><span data-stu-id="68c55-140">The **Download and Install** dialog appears.</span></span> <span data-ttu-id="68c55-141">Si está de acuerdo con los términos de la licencia, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="68c55-141">If you agree with the license terms, click **Install**.</span></span>  
  
7.  <span data-ttu-id="68c55-142">Cuando la extensión **Identity and Access** haya acabado de instalarse, reinicie Visual Studio en modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="68c55-142">When the **Identity and Access** extension has finished installing, restart Visual Studio in administrator mode.</span></span>  
  
## <a name="step-2--create-a-relying-party-aspnet-application"></a><span data-ttu-id="68c55-143">Paso 2 - Crear una aplicación ASP.NET de usuario de confianza</span><span class="sxs-lookup"><span data-stu-id="68c55-143">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
 <span data-ttu-id="68c55-144">Este paso describe la manera de crear una aplicación de formularios Web Forms ASP.NET de usuario de confianza que se integrará con WIF.</span><span class="sxs-lookup"><span data-stu-id="68c55-144">This step describes how to create a relying party ASP.NET Web Forms application that will integrate with WIF.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="68c55-145">Para crear una aplicación de ASP.NET sencilla</span><span class="sxs-lookup"><span data-stu-id="68c55-145">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="68c55-146">Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="68c55-146">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="68c55-147">En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="68c55-147">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="68c55-148">En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68c55-148">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-3--enable-local-development-sts-to-authenticate-users"></a><span data-ttu-id="68c55-149">Paso 3 - Habilitar STS de desarrollo local para autenticar usuarios</span><span class="sxs-lookup"><span data-stu-id="68c55-149">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
 <span data-ttu-id="68c55-150">Este paso describe cómo habilitar el STS de desarrollo local en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="68c55-150">This step describes how to enable Local Development STS in your application.</span></span> <span data-ttu-id="68c55-151">El STS de desarrollo local se habilita utilizando la extensión Identity and Access de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="68c55-151">Local Development STS is enabled by using the Identity and Access extension for Visual Studio.</span></span>  
  
#### <a name="to-enable-local-development-sts-in-your-aspnet-application"></a><span data-ttu-id="68c55-152">Para habilitar el STS de desarrollo local en la aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68c55-152">To enable Local Development STS in your ASP.NET application</span></span>  
  
1.  <span data-ttu-id="68c55-153">En Visual Studio, haga clic con el botón derecho en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="68c55-153">In Visual Studio, right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
2.  <span data-ttu-id="68c55-154">Aparecerá la ventana **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="68c55-154">The **Identity and Access** window appears.</span></span> <span data-ttu-id="68c55-155">En **Proveedores**, seleccione **Test your application with the Local Development STS** (Probar la aplicación con el STS de desarrollo local) y haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="68c55-155">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
## <a name="step-4--modify-your-aspnet-application-to-display-sign-in-status"></a><span data-ttu-id="68c55-156">Paso 4 - Modificar la aplicación ASP.NET para que muestre el estado de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="68c55-156">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
 <span data-ttu-id="68c55-157">Este paso describe la manera de modificar la aplicación ASP.NET para que muestre de manera dinámica si el usuario actual ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="68c55-157">This step describes how to modify your ASP.NET application to dynamically display whether the current user is signed in.</span></span> <span data-ttu-id="68c55-158">Una vez configurado el proveedor de STS, WIF controla las notificaciones de entrada.</span><span class="sxs-lookup"><span data-stu-id="68c55-158">Once your STS provider has been configured, WIF handles the incoming claims.</span></span> <span data-ttu-id="68c55-159">Ahora debe configurar el código de la aplicación para mostrar el resultado de la autenticación.</span><span class="sxs-lookup"><span data-stu-id="68c55-159">Now you need to configure your application’s code to display the result of the authentication.</span></span>  
  
#### <a name="to-display-sign-in-status"></a><span data-ttu-id="68c55-160">Para mostrar el estado de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="68c55-160">To display sign in status</span></span>  
  
1.  <span data-ttu-id="68c55-161">En Visual Studio, abra el archivo **Default.aspx** bajo el proyecto **TestApp**.</span><span class="sxs-lookup"><span data-stu-id="68c55-161">In Visual Studio, open the **Default.aspx** file under the **TestApp** project.</span></span>  
  
2.  <span data-ttu-id="68c55-162">Reemplace el marcado existente en el archivo **Default.aspx** con el siguiente marcado:</span><span class="sxs-lookup"><span data-stu-id="68c55-162">Replace the existing markup in the **Default.aspx** file with the following markup:</span></span>  
  
    ```  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3.  <span data-ttu-id="68c55-163">Guarde **Default.aspx** y abra su archivo de código subyacente denominado **Default.aspx.cs**.</span><span class="sxs-lookup"><span data-stu-id="68c55-163">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68c55-164">**Default.aspx.cs** puede estar oculto bajo **Default.aspx** en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="68c55-164">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="68c55-165">Si **Default.aspx.cs** no está visible, expanda **Default.aspx** haciendo clic en el triángulo que se encuentra al lado.</span><span class="sxs-lookup"><span data-stu-id="68c55-165">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
4.  <span data-ttu-id="68c55-166">Reemplace el código existente en **Default.aspx.cs** por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="68c55-166">Replace the existing code in **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="68c55-167">Guarde **Default.aspx.cs** y compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="68c55-167">Save **Default.aspx.cs**, and build the application.</span></span>  
  
## <a name="step-5--test-the-integration-between-wif-and-your-aspnet-application"></a><span data-ttu-id="68c55-168">Paso 5 - Probar la integración entre WIF y la aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68c55-168">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
 <span data-ttu-id="68c55-169">Este paso describe cómo puede probar la integración entre WIF y la aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="68c55-169">This step describes how you can test the integration between WIF and your ASP.NET application.</span></span>  
  
#### <a name="to-test-the-integration-between-wif-and-aspnet"></a><span data-ttu-id="68c55-170">Para probar la integración entre WIF y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68c55-170">To test the integration between WIF and ASP.NET</span></span>  
  
1.  <span data-ttu-id="68c55-171">En Visual Studio, presione **F5** para iniciar la depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="68c55-171">In Visual Studio, press **F5** to start debugging your application.</span></span> <span data-ttu-id="68c55-172">Si no se encuentra ningún error, se abrirá una nueva ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="68c55-172">If no errors are found, a new browser window will open.</span></span>  
  
2.  <span data-ttu-id="68c55-173">Puede observar que el explorador redirige de manera silenciosa la solicitud al STS y abre a continuación la página Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="68c55-173">You may notice that the browser silently redirects your request to the STS, and then opens the Default.aspx page.</span></span> <span data-ttu-id="68c55-174">Si WIF está configurado de manera adecuada, debería ver que el sitio muestra el texto siguiente: **"Ha iniciado sesión"**.</span><span class="sxs-lookup"><span data-stu-id="68c55-174">If WIF is properly configured, you should see the site display the following text: **"You are signed in"**.</span></span>
