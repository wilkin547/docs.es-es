---
title: Cómo habilitar la detección de reproducción de tokens
ms.date: 03/30/2017
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
author: BrucePerlerMS
ms.openlocfilehash: a357f153d61b6a8e1e105639bd68647dabdc26f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940483"
---
# <a name="how-to-enable-token-replay-detection"></a><span data-ttu-id="6520f-102">Cómo habilitar la detección de reproducción de tokens</span><span class="sxs-lookup"><span data-stu-id="6520f-102">How To: Enable Token Replay Detection</span></span>
## <a name="applies-to"></a><span data-ttu-id="6520f-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="6520f-103">Applies To</span></span>  
  
- <span data-ttu-id="6520f-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="6520f-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="6520f-105">Formularios Web Forms ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="6520f-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="6520f-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="6520f-106">Summary</span></span>  
 <span data-ttu-id="6520f-107">En este tema de procedimientos se detallan los procedimientos necesarios para habilitar la detección de reproducción de tokens en una aplicación ASP.NET que usa WIF.</span><span class="sxs-lookup"><span data-stu-id="6520f-107">This How-To provides detailed step-by-step procedures for enabling token replay detection in an ASP.NET application that uses WIF.</span></span> <span data-ttu-id="6520f-108">También se proporcionan instrucciones para probar la aplicación a fin de comprobar que esté habilitada la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="6520f-108">It also provides instructions for how to test the application to verify that token replay detection is enabled.</span></span> <span data-ttu-id="6520f-109">Esta sección de procedimientos no tiene instrucciones detalladas para crear un servicio de token de seguridad (STS) y en su lugar se utiliza el STS de desarrollo que se incluye con la extensión Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="6520f-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="6520f-110">El STS de desarrollo no realiza la autenticación real y está pensado únicamente para pruebas.</span><span class="sxs-lookup"><span data-stu-id="6520f-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="6520f-111">Para completar este procedimiento, tendrá que instalar la extensión Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="6520f-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="6520f-112">Se puede descargar desde la ubicación siguiente: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="6520f-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="6520f-113">Contenido</span><span class="sxs-lookup"><span data-stu-id="6520f-113">Contents</span></span>  
  
- <span data-ttu-id="6520f-114">Objetivos</span><span class="sxs-lookup"><span data-stu-id="6520f-114">Objectives</span></span>  
  
- <span data-ttu-id="6520f-115">Información general</span><span class="sxs-lookup"><span data-stu-id="6520f-115">Overview</span></span>  
  
- <span data-ttu-id="6520f-116">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="6520f-116">Summary of Steps</span></span>  
  
- <span data-ttu-id="6520f-117">Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar la detección de reproducción</span><span class="sxs-lookup"><span data-stu-id="6520f-117">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
- <span data-ttu-id="6520f-118">Paso 2 – Probar la solución</span><span class="sxs-lookup"><span data-stu-id="6520f-118">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="6520f-119">Objetivos</span><span class="sxs-lookup"><span data-stu-id="6520f-119">Objectives</span></span>  
  
- <span data-ttu-id="6520f-120">Crear una aplicación ASP.NET simple que use WIF y el STS de desarrollo desde la herramienta Identity and Access Tool</span><span class="sxs-lookup"><span data-stu-id="6520f-120">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
- <span data-ttu-id="6520f-121">Habilitar la detección de reproducción de tokens y comprobar que funciona</span><span class="sxs-lookup"><span data-stu-id="6520f-121">Enable token replay detection and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="6520f-122">Información general</span><span class="sxs-lookup"><span data-stu-id="6520f-122">Overview</span></span>  
 <span data-ttu-id="6520f-123">Los ataques de reproducción se producen cuando un cliente intenta autenticarse en un usuario de confianza con un token STS que ya ha usado.</span><span class="sxs-lookup"><span data-stu-id="6520f-123">A replay attack occurs when a client attempts to authenticate to a relying party with an STS token that the client has already used.</span></span> <span data-ttu-id="6520f-124">Para evitar este tipo de ataque, WIF contiene una caché de detección de reproducción de tokens STS ya usados.</span><span class="sxs-lookup"><span data-stu-id="6520f-124">To help prevent this attack, WIF contains a replay detection cache of previously used STS tokens.</span></span> <span data-ttu-id="6520f-125">Cuando está habilitada, la detección de reproducción comprueba el token de la solicitud entrante y verifica si el token ya se ha usado.</span><span class="sxs-lookup"><span data-stu-id="6520f-125">When enabled, replay detection checks the token of the incoming request and verifies whether or not the token has been previously used.</span></span> <span data-ttu-id="6520f-126">Si el token ya se ha usado, se rechaza la solicitud y se produce una excepción <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException>.</span><span class="sxs-lookup"><span data-stu-id="6520f-126">If the token has been used already, the request is refused and a <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> exception is thrown.</span></span>  
  
 <span data-ttu-id="6520f-127">En los pasos siguientes se muestran los cambios de configuración necesarios para habilitar la detección de reproducción.</span><span class="sxs-lookup"><span data-stu-id="6520f-127">The following steps demonstrate the configuration changes required to enable replay detection.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="6520f-128">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="6520f-128">Summary of Steps</span></span>  
  
- <span data-ttu-id="6520f-129">Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar la detección de reproducción</span><span class="sxs-lookup"><span data-stu-id="6520f-129">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
- <span data-ttu-id="6520f-130">Paso 2 – Probar la solución</span><span class="sxs-lookup"><span data-stu-id="6520f-130">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-replay-detection"></a><span data-ttu-id="6520f-131">Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar la detección de reproducción</span><span class="sxs-lookup"><span data-stu-id="6520f-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
 <span data-ttu-id="6520f-132">En este paso, creará una aplicación de formularios Web Forms de ASP.NET y modificará el archivo *Web.config* para habilitar la detección de reproducción.</span><span class="sxs-lookup"><span data-stu-id="6520f-132">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable replay detection.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="6520f-133">Para crear una aplicación de ASP.NET sencilla</span><span class="sxs-lookup"><span data-stu-id="6520f-133">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="6520f-134">Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6520f-134">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="6520f-135">En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="6520f-135">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3. <span data-ttu-id="6520f-136">En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6520f-136">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4. <span data-ttu-id="6520f-137">Haga clic con el botón derecho en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="6520f-137">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5. <span data-ttu-id="6520f-138">Aparecerá la ventana **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="6520f-138">The **Identity and Access** window appears.</span></span> <span data-ttu-id="6520f-139">En **Proveedores**, seleccione **Test your application with the Local Development STS** (Probar la aplicación con el STS de desarrollo local) y haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6520f-139">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6. <span data-ttu-id="6520f-140">Agregue el siguiente elemento **\<tokenReplayDetection>** al archivo de configuración *Web.config* inmediatamente después de los elementos **\<system.identityModel>** e **\<identityConfiguration>**, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="6520f-140">Add the following **\<tokenReplayDetection>** element to the *Web.config* configuration file immediately following the **\<system.identityModel>** and **\<identityConfiguration>** elements, like shown:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled="true"/>  
    ```  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="6520f-141">Paso 2 – Probar la solución</span><span class="sxs-lookup"><span data-stu-id="6520f-141">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="6520f-142">En este paso, probará la aplicación ASP.NET habilitada para WIF a fin de comprobar que se ha habilitado la detección de reproducción.</span><span class="sxs-lookup"><span data-stu-id="6520f-142">In this step, you will test your WIF-enabled ASP.NET application to verify that replay detection has been enabled.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-replay-detection"></a><span data-ttu-id="6520f-143">Para probar la aplicación ASP.NET habilitada para WIF para la detección de reproducción</span><span class="sxs-lookup"><span data-stu-id="6520f-143">To test your WIF-enabled ASP.NET application for replay detection</span></span>  
  
1. <span data-ttu-id="6520f-144">Presione la tecla **F5** para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="6520f-144">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="6520f-145">Debe aparecer la página principal de ASP.NET predeterminada y se le debe autenticar automáticamente con el nombre de usuario *Terry*, que es el usuario predeterminado devuelto por el STS de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="6520f-145">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2. <span data-ttu-id="6520f-146">Haga clic en el botón **Atrás** del explorador.</span><span class="sxs-lookup"><span data-stu-id="6520f-146">Press the browser’s **Back** button.</span></span> <span data-ttu-id="6520f-147">Debe estar presente con un **Server Error in '/' Application** página con la siguiente descripción: *ID1062: Se detectó la reproducción para: Símbolo (token): 'System.IdentityModel.Tokens.SamlSecurityToken'*, seguido de un *AssertionId* y un *emisor*.</span><span class="sxs-lookup"><span data-stu-id="6520f-147">You should be presented with a **Server Error in ‘/’ Application** page with the following description: *ID1062: Replay has been detected for: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, followed by an *AssertionId* and an *Issuer*.</span></span>  
  
     <span data-ttu-id="6520f-148">Está viendo esta página de error porque se ha producido una excepción de tipo <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> al detectarse la reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="6520f-148">You are seeing this error page because an exception of type <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> was thrown when the token replay was detected.</span></span> <span data-ttu-id="6520f-149">Este error se produce porque está intentando volver a enviar la solicitud POST inicial cuando el token se presenta por primera vez.</span><span class="sxs-lookup"><span data-stu-id="6520f-149">This error occurs because you are attempting to re-send the initial POST request when the token was first presented.</span></span> <span data-ttu-id="6520f-150">El botón **Atrás** no provocará este comportamiento en las solicitudes siguientes al servidor.</span><span class="sxs-lookup"><span data-stu-id="6520f-150">The **Back** button will not cause this behavior on subsequent requests to the server.</span></span>
