---
title: 'Cómo: crear aplicaciones ASP.NET para notificaciones mediante la autenticación de Windows'
ms.date: 03/30/2017
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
author: BrucePerlerMS
ms.openlocfilehash: 2c7877c452c729b30029cad1a8e17600f3dc9661
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198533"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a><span data-ttu-id="1efa7-102">Cómo: crear aplicaciones ASP.NET para notificaciones mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="1efa7-102">How To: Build Claims-Aware ASP.NET Application Using Windows Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="1efa7-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="1efa7-103">Applies To</span></span>  
  
-   <span data-ttu-id="1efa7-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="1efa7-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="1efa7-105">Formularios Web Forms ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="1efa7-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="1efa7-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="1efa7-106">Summary</span></span>  
 <span data-ttu-id="1efa7-107">Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación de formularios Web Forms ASP.NET para notificaciones que usa la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1efa7-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Windows authentication.</span></span> <span data-ttu-id="1efa7-108">También proporciona instrucciones para probar la aplicación para comprobar que las notificaciones se presentan cuando un usuario inicia sesión con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1efa7-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in using Windows authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="1efa7-109">Contenido</span><span class="sxs-lookup"><span data-stu-id="1efa7-109">Contents</span></span>  
  
-   <span data-ttu-id="1efa7-110">Objetivos</span><span class="sxs-lookup"><span data-stu-id="1efa7-110">Objectives</span></span>  
  
-   <span data-ttu-id="1efa7-111">Información general</span><span class="sxs-lookup"><span data-stu-id="1efa7-111">Overview</span></span>  
  
-   <span data-ttu-id="1efa7-112">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="1efa7-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="1efa7-113">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1efa7-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="1efa7-114">Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="1efa7-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="1efa7-115">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="1efa7-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="1efa7-116">Objetivos</span><span class="sxs-lookup"><span data-stu-id="1efa7-116">Objectives</span></span>  
  
-   <span data-ttu-id="1efa7-117">Configurar una aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="1efa7-117">Configure an ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
-   <span data-ttu-id="1efa7-118">Probar la aplicación de formularios Web Forms ASP.NET para ver si funciona correctamente</span><span class="sxs-lookup"><span data-stu-id="1efa7-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="1efa7-119">Información general</span><span class="sxs-lookup"><span data-stu-id="1efa7-119">Overview</span></span>  
 <span data-ttu-id="1efa7-120">En .NET 4.5, WIF y su autorización basada en notificaciones se han incluido como parte integral del marco.</span><span class="sxs-lookup"><span data-stu-id="1efa7-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="1efa7-121">Anteriormente, si quería notificaciones de un usuario de ASP.NET, tenía que instalar WIF y, después, convertir las interfaces a objetos de entidad de seguridad como `Thread.CurrentPrincipal` o `HttpContext.Current.User`.</span><span class="sxs-lookup"><span data-stu-id="1efa7-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="1efa7-122">Ahora, estos objetos de entidad de seguridad sirven las notificaciones automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1efa7-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="1efa7-123">La autenticación de Windows se ha beneficiado de la inclusión de WIF en .NET 4.5, ya que todos los usuarios autenticados mediante credenciales de Windows automáticamente tienen notificaciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="1efa7-123">Windows authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Windows credentials automatically have claims associated with them.</span></span> <span data-ttu-id="1efa7-124">Puede empezar a usar estas notificaciones inmediatamente en una aplicación de ASP.NET que use la autenticación de Windows, como se muestra en este tema de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="1efa7-124">You can begin using these claims immediately in an ASP.NET application that uses Windows authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="1efa7-125">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="1efa7-125">Summary of Steps</span></span>  
  
-   <span data-ttu-id="1efa7-126">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1efa7-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="1efa7-127">Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="1efa7-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="1efa7-128">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="1efa7-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="1efa7-129">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1efa7-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="1efa7-130">En este paso creará una aplicación de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1efa7-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="1efa7-131">Para crear una aplicación de ASP.NET sencilla</span><span class="sxs-lookup"><span data-stu-id="1efa7-131">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="1efa7-132">Inicie Visual Studio y, después, haga clic en **Archivo**, **Nuevo** y en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="1efa7-132">Start Visual Studio, then click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="1efa7-133">En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="1efa7-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="1efa7-134">En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1efa7-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="1efa7-135">Después de que se haya creado el proyecto **TestApp**, haga clic en él en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="1efa7-135">After the **TestApp** project has been created, click on it in **Solution Explorer**.</span></span> <span data-ttu-id="1efa7-136">Las propiedades del proyecto aparecerán en el panel **Propiedades** debajo del **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="1efa7-136">The project’s properties will appear in the **Properties** pane below **Solution Explorer**.</span></span> <span data-ttu-id="1efa7-137">Establezca la propiedad **Autenticación de Windows** en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="1efa7-137">Set the **Windows Authentication** property to **Enabled**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="1efa7-138">La autenticación de Windows está deshabilitada de manera predeterminada en las nuevas aplicaciones ASP.NET, por lo que debe habilitarla manualmente.</span><span class="sxs-lookup"><span data-stu-id="1efa7-138">Windows authentication is disabled by default in new ASP.NET applications, so you must manually enable it.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="1efa7-139">Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="1efa7-139">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
 <span data-ttu-id="1efa7-140">En este paso agregará una entrada de configuración al archivo de configuración *Web.config* y modificará el archivo *Default.aspx* para que se muestre la información de notificaciones de una cuenta.</span><span class="sxs-lookup"><span data-stu-id="1efa7-140">In this step you will add a configuration entry to the *Web.config* configuration file and modify the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a><span data-ttu-id="1efa7-141">Para configurar la aplicación ASP.NET para notificaciones mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="1efa7-141">To configure ASP.NET application for claims using Windows authentication</span></span>  
  
1.  <span data-ttu-id="1efa7-142">En el archivo *Default.aspx* del proyecto **TestApp**, reemplace el marcado existente por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1efa7-142">In the **TestApp** project’s *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Windows authenticated user.          
        </p>  
        <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
     <span data-ttu-id="1efa7-143">Este paso agrega un control GridView a la página *Default.aspx* que se va a rellenar con las notificaciones recuperadas de la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1efa7-143">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Windows authentication.</span></span>  
  
2.  <span data-ttu-id="1efa7-144">Guarde el archivo *Default.aspx* y abra su archivo de código subyacente denominado *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="1efa7-144">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="1efa7-145">Reemplace el código existente por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1efa7-145">Replace the existing code with the following:</span></span>  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        public partial class _Default : Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;  
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="1efa7-146">El código anterior mostrará las notificaciones sobre un usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="1efa7-146">The above code will display claims about an authenticated user.</span></span>  
  
3.  <span data-ttu-id="1efa7-147">Para cambiar el tipo de autenticación de la aplicación, modifique el bloque **\<authentication>** en la sección **\<system.web>** del archivo *Web.config* de la raíz del proyecto, de manera que solo incluya la siguiente entrada de configuración:</span><span class="sxs-lookup"><span data-stu-id="1efa7-147">To change the application’s authentication type, modify the **\<authentication>** block in the **\<system.web>** section of the project’s root *Web.config* file so that it only includes the following configuration entry:</span></span>  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4.  <span data-ttu-id="1efa7-148">Por último, modifique el bloque **\<authorization>** en la sección **\<system.web>** del mismo archivo *Web.config* para forzar la autenticación:</span><span class="sxs-lookup"><span data-stu-id="1efa7-148">Finally, modify the **\<authorization>** block in the **\<system.web>** section of the same *Web.config* file to force authentication:</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="1efa7-149">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="1efa7-149">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="1efa7-150">En este paso se prueba la aplicación de formularios Web Forms ASP.NET y se comprueba que se presentan notificaciones cuando un usuario inicia sesión con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1efa7-150">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Windows authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="1efa7-151">Para probar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="1efa7-151">To test your ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
1.  <span data-ttu-id="1efa7-152">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1efa7-152">Press **F5** to build and run the application.</span></span> <span data-ttu-id="1efa7-153">Debe aparecer con *Default.aspx*, y su nombre de cuenta Windows (incluido el nombre de dominio) ya debe aparecer como el usuario autenticado en la parte superior derecha de la página.</span><span class="sxs-lookup"><span data-stu-id="1efa7-153">You should be presented with *Default.aspx*, and your Windows account name (including domain name) should already appear as the authenticated user in the top right of the page.</span></span> <span data-ttu-id="1efa7-154">El contenido de la página debe incluir una tabla en la que aparecen las notificaciones que se han recuperado de su cuenta Windows.</span><span class="sxs-lookup"><span data-stu-id="1efa7-154">The page’s content should include a table filled with claims retrieved from your Windows account.</span></span>
