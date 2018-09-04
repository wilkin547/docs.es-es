---
title: 'Cómo: crear aplicaciones de formularios Web de ASP.NET para notificaciones mediante WIF'
ms.date: 03/30/2017
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 764e7fba31a7fb3fc40ec85ab4d0fb6e18e57390
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519050"
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a><span data-ttu-id="4752e-102">Cómo: crear aplicaciones de formularios Web de ASP.NET para notificaciones mediante WIF</span><span class="sxs-lookup"><span data-stu-id="4752e-102">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="4752e-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="4752e-103">Applies To</span></span>  
  
-   <span data-ttu-id="4752e-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="4752e-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="4752e-105">Formularios Web Forms ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="4752e-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="4752e-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="4752e-106">Summary</span></span>  
 <span data-ttu-id="4752e-107">Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación de formularios Web Forms ASP.NET para notificaciones.</span><span class="sxs-lookup"><span data-stu-id="4752e-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET Web Forms application.</span></span> <span data-ttu-id="4752e-108">También proporciona instrucciones sobre cómo probar la aplicación sencilla de formularios Web Forms ASP.NET para notificaciones para obtener una implementación correcta de la autenticación federada.</span><span class="sxs-lookup"><span data-stu-id="4752e-108">It also provides instructions for how to test the simple claims-aware ASP.NET Web Forms application for successful implementation of federated authentication.</span></span> <span data-ttu-id="4752e-109">Este tema de procedimientos no tiene instrucciones detalladas para crear un Servicio de tokens de seguridad (STS) y presupone que ya ha configurado uno.</span><span class="sxs-lookup"><span data-stu-id="4752e-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="4752e-110">Contenido</span><span class="sxs-lookup"><span data-stu-id="4752e-110">Contents</span></span>  
  
-   <span data-ttu-id="4752e-111">Objetivos</span><span class="sxs-lookup"><span data-stu-id="4752e-111">Objectives</span></span>  
  
-   <span data-ttu-id="4752e-112">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="4752e-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4752e-113">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4752e-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="4752e-114">Paso 2: Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4752e-114">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="4752e-115">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="4752e-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="4752e-116">Objetivos</span><span class="sxs-lookup"><span data-stu-id="4752e-116">Objectives</span></span>  
  
-   <span data-ttu-id="4752e-117">Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4752e-117">Configure ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="4752e-118">Probar una aplicación de formularios Web Forms ASP.NET para notificaciones correcta</span><span class="sxs-lookup"><span data-stu-id="4752e-118">Test successful claims-aware ASP.NET Web Forms application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="4752e-119">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="4752e-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4752e-120">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4752e-120">Step 1 – Create Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="4752e-121">Paso 2: Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación federada</span><span class="sxs-lookup"><span data-stu-id="4752e-121">Step 2 – Configure ASP.NET Web Forms Application for Federated Authentication</span></span>  
  
-   <span data-ttu-id="4752e-122">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="4752e-122">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="4752e-123">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4752e-123">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="4752e-124">En este paso creará una aplicación de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4752e-124">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="4752e-125">Para crear una aplicación de ASP.NET sencilla</span><span class="sxs-lookup"><span data-stu-id="4752e-125">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="4752e-126">Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4752e-126">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="4752e-127">En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="4752e-127">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="4752e-128">En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4752e-128">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a><span data-ttu-id="4752e-129">Paso 2: Configurar una aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4752e-129">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="4752e-130">En este paso agregará entradas de configuración al archivo de configuración *Web.config* de su aplicación de formularios Web Forms ASP.NET para notificaciones.</span><span class="sxs-lookup"><span data-stu-id="4752e-130">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET Web Forms application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a><span data-ttu-id="4752e-131">Para configurar la aplicación ASP.NET para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4752e-131">To configure ASP.NET application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="4752e-132">Agregue las siguientes entradas de la sección de configuración al archivo de configuración *Web.config* inmediatamente después del elemento de apertura **\<configuration>**:</span><span class="sxs-lookup"><span data-stu-id="4752e-132">Add the following configuration section entries to the *Web.config* configuration file immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  <span data-ttu-id="4752e-133">Agregue un elemento **\<location>** que permita el acceso a los metadatos de federación de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="4752e-133">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3.  <span data-ttu-id="4752e-134">Agregue las siguientes entradas de configuración dentro de los elementos **\<system.web>** para denegar usuarios, deshabilitar la autenticación nativa y habilitar WIF para administrar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="4752e-134">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  <span data-ttu-id="4752e-135">Agregue un elemento **\<system.webServer>** que defina los módulos para la autenticación federada.</span><span class="sxs-lookup"><span data-stu-id="4752e-135">Add a **\<system.webServer>** element that defines the modules for federated authentication.</span></span> <span data-ttu-id="4752e-136">Tenga en cuenta que el atributo *PublicKeyToken* debe ser el mismo que el atributo *PublicKeyToken* para las entradas **\<configSections>** que se han agregado anteriormente:</span><span class="sxs-lookup"><span data-stu-id="4752e-136">Note that the *PublicKeyToken* attribute must be the same as the *PublicKeyToken* attribute for the **\<configSections>** entries added earlier:</span></span>  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  <span data-ttu-id="4752e-137">Agregue las siguientes entradas de configuración relacionadas con Windows Identity Foundation y asegúrese de que su URL de la aplicación ASP.NET y el número de puerto coinciden con los valores de la entrada **\<audienceUris>**, el atributo **realm** del elemento **\<wsFederation>** y el atributo **reply** del elemento **\<wsFederation>**.</span><span class="sxs-lookup"><span data-stu-id="4752e-137">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="4752e-138">También asegúrese de que el valor **issuer** se adapta a su URL del servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="4752e-138">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
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
            <cookieHandler requireSsl="true" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="true" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
6.  <span data-ttu-id="4752e-139">Agregue una referencia al ensamblado <xref:System.IdentityModel>.</span><span class="sxs-lookup"><span data-stu-id="4752e-139">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
7.  <span data-ttu-id="4752e-140">Compile la solución y asegúrese de que no existan errores.</span><span class="sxs-lookup"><span data-stu-id="4752e-140">Compile the solution to make sure there are no errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="4752e-141">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="4752e-141">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="4752e-142">En este paso probará la aplicación de formularios Web Forms ASP.NET configurada para la autenticación basada en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="4752e-142">In this step you will test your ASP.NET Web Forms application configured for claims-based authentication.</span></span> <span data-ttu-id="4752e-143">Para realizar una prueba básica, agregará código que muestra notificaciones en el token emitido mediante el servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="4752e-143">To perform a basic test, you will add code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a><span data-ttu-id="4752e-144">Para probar su aplicación de formularios Web Forms ASP.NET para la autenticación basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="4752e-144">To test your ASP.NET Web Form application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="4752e-145">Abra el archivo **Default.aspx** en el proyecto **TestApp** y reemplace su marcado existente por el marcado siguiente:</span><span class="sxs-lookup"><span data-stu-id="4752e-145">Open the **Default.aspx** file under the **TestApp** project and replace its existing markup with the following markup:</span></span>  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2.  <span data-ttu-id="4752e-146">Guarde **Default.aspx** y abra su archivo de código subyacente denominado **Default.aspx.cs**.</span><span class="sxs-lookup"><span data-stu-id="4752e-146">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4752e-147">**Default.aspx.cs** puede estar oculto bajo **Default.aspx** en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="4752e-147">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="4752e-148">Si **Default.aspx.cs** no está visible, expanda **Default.aspx** haciendo clic en el triángulo que se encuentra al lado.</span><span class="sxs-lookup"><span data-stu-id="4752e-148">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
3.  <span data-ttu-id="4752e-149">Reemplace el código existente en el método **Page_Load** de **Default.aspx.cs** por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4752e-149">Replace the existing code in the **Page_Load** method of **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="4752e-150">Guarde **Default.aspx.cs** y compile la solución.</span><span class="sxs-lookup"><span data-stu-id="4752e-150">Save **Default.aspx.cs**, and build the solution.</span></span>  
  
5.  <span data-ttu-id="4752e-151">Presione la tecla **F5** para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="4752e-151">Run the solution by pressing the **F5** key.</span></span>  
  
6.  <span data-ttu-id="4752e-152">Debe estar presente en la página que muestra las notificaciones del token que ha emitido mediante el servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4752e-152">You should be presented with the page that displays the claims in the token that was issued to you by the Security Token Service.</span></span>
