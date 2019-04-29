---
title: Cómo transformar las notificaciones entrantes
ms.date: 03/30/2017
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
author: BrucePerlerMS
ms.openlocfilehash: f836356125f1462f302b7e9f45a841c869c9a690
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940444"
---
# <a name="how-to-transform-incoming-claims"></a><span data-ttu-id="30543-102">Cómo transformar las notificaciones entrantes</span><span class="sxs-lookup"><span data-stu-id="30543-102">How To: Transform Incoming Claims</span></span>
## <a name="applies-to"></a><span data-ttu-id="30543-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="30543-103">Applies To</span></span>  
  
- <span data-ttu-id="30543-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="30543-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="30543-105">Formularios Web Forms ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="30543-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="30543-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="30543-106">Summary</span></span>  
 <span data-ttu-id="30543-107">Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación de formularios Web Forms ASP.NET para notificaciones y transformar las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="30543-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application and transforming incoming claims.</span></span> <span data-ttu-id="30543-108">También se proporcionan instrucciones sobre cómo probar la aplicación para comprobar que las notificaciones transformadas están presentes cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="30543-108">It also provides instructions for how to test the application to verify that transformed claims are presented when the application is run.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="30543-109">Contenido</span><span class="sxs-lookup"><span data-stu-id="30543-109">Contents</span></span>  
  
- <span data-ttu-id="30543-110">Objetivos</span><span class="sxs-lookup"><span data-stu-id="30543-110">Objectives</span></span>  
  
- <span data-ttu-id="30543-111">Información general</span><span class="sxs-lookup"><span data-stu-id="30543-111">Overview</span></span>  
  
- <span data-ttu-id="30543-112">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="30543-112">Summary of Steps</span></span>  
  
- <span data-ttu-id="30543-113">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30543-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
- <span data-ttu-id="30543-114">Paso 2: Implementar la transformación de notificaciones con un elemento ClaimsAuthenticationManager personalizado</span><span class="sxs-lookup"><span data-stu-id="30543-114">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
- <span data-ttu-id="30543-115">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="30543-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="30543-116">Objetivos</span><span class="sxs-lookup"><span data-stu-id="30543-116">Objectives</span></span>  
  
- <span data-ttu-id="30543-117">Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="30543-117">Configure an ASP.NET Web Forms application for claims-based authentication</span></span>  
  
- <span data-ttu-id="30543-118">Transformar las notificaciones entrantes agregando una notificación de rol de administrador</span><span class="sxs-lookup"><span data-stu-id="30543-118">Transform incoming claims by adding an Administrator role claim</span></span>  
  
- <span data-ttu-id="30543-119">Probar la aplicación de formularios Web Forms ASP.NET para ver si funciona correctamente</span><span class="sxs-lookup"><span data-stu-id="30543-119">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="30543-120">Información general</span><span class="sxs-lookup"><span data-stu-id="30543-120">Overview</span></span>  
 <span data-ttu-id="30543-121">WIF expone una clase denominada <xref:System.Security.Claims.ClaimsAuthenticationManager> que permite a los usuarios modificar notificaciones antes de que se presenten en una aplicación de usuario de confianza (RP).</span><span class="sxs-lookup"><span data-stu-id="30543-121">WIF exposes a class named <xref:System.Security.Claims.ClaimsAuthenticationManager> that enables users to modify claims before they are presented to a relying party (RP) application.</span></span> <span data-ttu-id="30543-122"><xref:System.Security.Claims.ClaimsAuthenticationManager> es útil para la separación de intereses entre la autenticación y el código de la aplicación subyacente.</span><span class="sxs-lookup"><span data-stu-id="30543-122">The <xref:System.Security.Claims.ClaimsAuthenticationManager> is useful for separation of concerns between authentication and the underlying application code.</span></span> <span data-ttu-id="30543-123">En el ejemplo siguiente se muestra cómo agregar un rol a las notificaciones en la <xref:System.Security.Claims.ClaimsPrincipal> entrante que el RP puede necesitar.</span><span class="sxs-lookup"><span data-stu-id="30543-123">The example below demonstrates how to add a role to the claims in the incoming <xref:System.Security.Claims.ClaimsPrincipal> that may be required by the RP.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="30543-124">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="30543-124">Summary of Steps</span></span>  
  
- <span data-ttu-id="30543-125">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30543-125">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
- <span data-ttu-id="30543-126">Paso 2: Implementar la transformación de notificaciones con un elemento ClaimsAuthenticationManager personalizado</span><span class="sxs-lookup"><span data-stu-id="30543-126">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
- <span data-ttu-id="30543-127">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="30543-127">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="30543-128">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="30543-128">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="30543-129">En este paso creará una aplicación de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30543-129">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="30543-130">Para crear una aplicación de ASP.NET sencilla</span><span class="sxs-lookup"><span data-stu-id="30543-130">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="30543-131">Inicie Visual Studio como administrador con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="30543-131">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2. <span data-ttu-id="30543-132">En Visual Studio, haga clic en **Archivo**, en **Nuevo** y, después, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="30543-132">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="30543-133">En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="30543-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
4. <span data-ttu-id="30543-134">En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30543-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
5. <span data-ttu-id="30543-135">Haga clic con el botón derecho en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="30543-135">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6. <span data-ttu-id="30543-136">Aparecerá la ventana **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="30543-136">The **Identity and Access** window appears.</span></span> <span data-ttu-id="30543-137">En **Proveedores**, seleccione **Test your application with the Local Development STS** (Probar la aplicación con el STS de desarrollo local) y haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="30543-137">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
7. <span data-ttu-id="30543-138">En el archivo *Default.aspx*, reemplace el marcado existente por el siguiente, después guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="30543-138">In the *Default.aspx* file, replace the existing markup with the following, then save the file:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
          <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
8. <span data-ttu-id="30543-139">Abra el archivo de código subyacente denominado *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="30543-139">Open the code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="30543-140">Reemplace el código existente por el siguiente y, después, guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="30543-140">Replace the existing code with the following, then save the file:</span></span>  
  
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
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="30543-141">Paso 2: Implementar la transformación de notificaciones con un elemento ClaimsAuthenticationManager personalizado</span><span class="sxs-lookup"><span data-stu-id="30543-141">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
 <span data-ttu-id="30543-142">En este paso reemplazará la función predeterminada en la clase <xref:System.Security.Claims.ClaimsAuthenticationManager> para agregar un rol de administrador a la entidad de seguridad entrante.</span><span class="sxs-lookup"><span data-stu-id="30543-142">In this step you will override default functionality in the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to add an Administrator role to the incoming Principal.</span></span>  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="30543-143">Para implementar la transformación de notificaciones con un elemento ClaimsAuthenticationManager personalizado</span><span class="sxs-lookup"><span data-stu-id="30543-143">To implement claims transformation using a custom ClaimsAuthenticationManager</span></span>  
  
1. <span data-ttu-id="30543-144">En Visual Studio, haga clic con el botón derecho en la solución, haga clic en **Agregar** y, después, en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="30543-144">In Visual Studio, right-click the on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2. <span data-ttu-id="30543-145">En la ventana **Agregar nuevo proyecto**, seleccione **Biblioteca de clases** en la lista de plantillas de **Visual C#**, escriba `ClaimsTransformation` y pulse **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30543-145">In the **Add New Project** window, select **Class Library** from the **Visual C#** templates list, enter `ClaimsTransformation`, and then press **OK**.</span></span> <span data-ttu-id="30543-146">El nuevo proyecto se creará en la carpeta de la solución.</span><span class="sxs-lookup"><span data-stu-id="30543-146">The new project will be created in your solution folder.</span></span>  
  
3. <span data-ttu-id="30543-147">Haga clic con el botón derecho en **Referencias** debajo del proyecto **ClaimsTransformation** y, después, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="30543-147">Right-click on **References** under the **ClaimsTransformation** project, and then click **Add Reference**.</span></span>  
  
4. <span data-ttu-id="30543-148">En la ventana **Administrador de referencias**, seleccione **System.IdentityModel** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30543-148">In the **Reference Manager** window, select **System.IdentityModel**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="30543-149">Abra **Class1.cs**, o si no existe, haga clic con el botón derecho en **ClaimsTransformation**, en **Agregar** y, después, en **Clase...**</span><span class="sxs-lookup"><span data-stu-id="30543-149">Open **Class1.cs**, or if it doesn’t exist, right-click **ClaimsTransformation**, click **Add**, then click **Class…**</span></span>  
  
6. <span data-ttu-id="30543-150">Agregue lo siguiente mediante las directivas al archivo de código:</span><span class="sxs-lookup"><span data-stu-id="30543-150">Add the following using directives to the code file:</span></span>  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7. <span data-ttu-id="30543-151">Agregue la siguiente clase y método en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="30543-151">Add the following class and method in the code file.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="30543-152">El código siguiente se muestra solo con fines demostrativos; asegúrese de que comprueba sus permisos previstos en el código de producción.</span><span class="sxs-lookup"><span data-stu-id="30543-152">The following code is for demonstration purposes only; make sure that you verify your intended permissions in production code.</span></span>  
  
    ```csharp  
    public class ClaimsTransformationModule : ClaimsAuthenticationManager  
    {  
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)  
        {  
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)  
            {  
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));  
            }  
  
            return incomingPrincipal;  
        }  
    }  
    ```  
  
8. <span data-ttu-id="30543-153">Guarde el archivo y compile el proyecto **ClaimsTransformation**.</span><span class="sxs-lookup"><span data-stu-id="30543-153">Save the file and build the **ClaimsTransformation** project.</span></span>  
  
9. <span data-ttu-id="30543-154">En su proyecto de ASP.NET **TestApp**, haga clic con el botón derecho en Referencias y, después, haga clic en **Agregar referencias**.</span><span class="sxs-lookup"><span data-stu-id="30543-154">In your **TestApp** ASP.NET project, right-click on References, and then click **Add Reference**.</span></span>  
  
10. <span data-ttu-id="30543-155">En la ventana **Administrador de referencias**, seleccione **Solución** del menú de la izquierda, seleccione **ClaimsTransformation** de las opciones que aparecen y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30543-155">In the **Reference Manager** window, select **Solution** from the left menu, select **ClaimsTransformation** from the populated options, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="30543-156">En el archivo **Web.config** raíz, vaya a la entrada **\<system.identityModel>**.</span><span class="sxs-lookup"><span data-stu-id="30543-156">In the root **Web.config** file, navigate to the **\<system.identityModel>** entry.</span></span> <span data-ttu-id="30543-157">Dentro de los elementos **\<identityConfiguration>**, agregue la línea siguiente y guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="30543-157">Within the **\<identityConfiguration>** elements, add the following line and save the file:</span></span>  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="30543-158">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="30543-158">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="30543-159">En este paso se prueba la aplicación de formularios Web Forms ASP.NET y se comprueba que se presentan notificaciones cuando un usuario inicia sesión con la autenticación de formularios.</span><span class="sxs-lookup"><span data-stu-id="30543-159">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="30543-160">Para probar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios</span><span class="sxs-lookup"><span data-stu-id="30543-160">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1. <span data-ttu-id="30543-161">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="30543-161">Press **F5** to build and run the application.</span></span> <span data-ttu-id="30543-162">Debe estar presente con *Default.aspx*.</span><span class="sxs-lookup"><span data-stu-id="30543-162">You should be presented with *Default.aspx*.</span></span>  
  
2. <span data-ttu-id="30543-163">En la página *Default.aspx*, debería ver una tabla debajo del título **Sus notificaciones** con la información de notificaciones **Emisor**, **OriginalIssuer**, **Tipo**, **Valor** y **ValueType** sobre la cuenta.</span><span class="sxs-lookup"><span data-stu-id="30543-163">On the *Default.aspx* page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span> <span data-ttu-id="30543-164">La última fila debe estar presente de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="30543-164">The last row should be presented in the following way:</span></span>  
  
    ||||||  
    |-|-|-|-|-|  
    |<span data-ttu-id="30543-165">LOCAL AUTHORITY</span><span class="sxs-lookup"><span data-stu-id="30543-165">LOCAL AUTHORITY</span></span>|<span data-ttu-id="30543-166">LOCAL AUTHORITY</span><span class="sxs-lookup"><span data-stu-id="30543-166">LOCAL AUTHORITY</span></span>|`http://schemas.microsoft.com/ws/2008/06/identity/claims/role`|<span data-ttu-id="30543-167">Administrador</span><span class="sxs-lookup"><span data-stu-id="30543-167">Admin</span></span>|<https://www.w3.org/2001/XMLSchema#string>|
