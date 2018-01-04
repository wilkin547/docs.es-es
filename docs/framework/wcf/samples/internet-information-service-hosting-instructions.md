---
title: Instrucciones de hospedaje Internet Information Services
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de7dc897aa435d62c04c2e6a3ca82adf3a637a2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="cee8e-102">Instrucciones de hospedaje Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="cee8e-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="cee8e-103">Para ejecutar los ejemplos que son hospedados por Internet Information Services (IIS), debe asegurarse de que IIS está instalado correctamente y se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="cee8e-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="cee8e-104">Para instalar la versión 7.5 de IIS en Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="cee8e-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="cee8e-105">De **el administrador del servidor**, seleccione **Roles.**</span><span class="sxs-lookup"><span data-stu-id="cee8e-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="cee8e-106">En **resumen de funciones**, haga clic en **agregar Roles**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="cee8e-107">Haga clic en **siguiente** para mostrar la **seleccionar Roles de servidor** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cee8e-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="cee8e-108">Seleccione **Application Server** desde el **Roles** lista y, a continuación, haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el Rol de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cee8e-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="cee8e-109">Seleccione el **servidor Web (IIS)** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="cee8e-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="cee8e-110">Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar características requeridas**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="cee8e-111">Haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el rol de servidor Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="cee8e-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="cee8e-112">Expanda **herramientas de administración**y, a continuación, expanda **compatibilidad con la administración de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="cee8e-113">Seleccione **IIS herramientas de Scripting 6**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="cee8e-114">Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar servicios de rol requeridos**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="cee8e-115">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-115">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="cee8e-116">Si el resumen de selecciones es correcto, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="cee8e-117">Cuando se completa la instalación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="cee8e-118">Para instalar IIS versión 7.5 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="cee8e-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1.  <span data-ttu-id="cee8e-119">Haga clic en **iniciar**y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="cee8e-120">Abra la **programas** grupo.</span><span class="sxs-lookup"><span data-stu-id="cee8e-120">Open the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="cee8e-121">En **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="cee8e-122">El **User Account Control** se muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cee8e-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="cee8e-123">Haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-123">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="cee8e-124">El **las características de Windows** se muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cee8e-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="cee8e-125">Expanda el elemento con la etiqueta **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="cee8e-126">Expanda el elemento con la etiqueta **servicios World Wide Web**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="cee8e-127">Expanda el elemento con la etiqueta **Application Development Features**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="cee8e-128">Asegúrese de que los siguientes elementos están seleccionados:</span><span class="sxs-lookup"><span data-stu-id="cee8e-128">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="cee8e-129">**Extensibilidad de .NET**</span><span class="sxs-lookup"><span data-stu-id="cee8e-129">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="cee8e-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="cee8e-130">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="cee8e-131">**Extensiones ISAPI**</span><span class="sxs-lookup"><span data-stu-id="cee8e-131">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="cee8e-132">**Filtros ISAPI**</span><span class="sxs-lookup"><span data-stu-id="cee8e-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="cee8e-133">En el elemento con la etiqueta **servicios World Wide Web**, expanda **características Http comunes**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="cee8e-134">Asegúrese de que **contenido estático** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cee8e-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="cee8e-135">En el elemento con la etiqueta **servicios World Wide Web**, expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="cee8e-136">Asegúrese de que **autenticación de Windows** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cee8e-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="cee8e-137">En el **Internet Information Services** directory, expanda el elemento con la etiqueta **herramientas de administración Web**y, a continuación, seleccione **consola de administración de IIS**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="cee8e-138">Expanda el elemento con la etiqueta **compatibilidad con la administración de IIS 6**y, a continuación, seleccione **herramientas de Scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="cee8e-139">En el **Internet Information Services** directory, expanda el elemento con la etiqueta **Microsoft .NET Framework 3.5.1**y, a continuación, seleccione **activación Http de Windows Communication Foundation**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="cee8e-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="cee8e-141">Para instalar la versión de IIS 7.0 en Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="cee8e-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="cee8e-142">De **el administrador del servidor**, seleccione **Roles**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="cee8e-143">En **resumen de funciones**, haga clic en **agregar Roles**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="cee8e-144">Haga clic en **siguiente** para mostrar la **seleccionar Roles de servidor** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cee8e-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="cee8e-145">Seleccione **Application Server** desde el **Roles** lista y, a continuación, haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el Rol de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cee8e-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="cee8e-146">Seleccione **servidor Web (IIS)** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="cee8e-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="cee8e-147">Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar características requeridas**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="cee8e-148">Haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el rol de servidor Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="cee8e-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="cee8e-149">Expanda **herramientas de administración**y, a continuación, expanda **compatibilidad con la administración de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="cee8e-150">Seleccione **IIS herramientas de Scripting 6**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="cee8e-151">Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar servicios de rol requeridos**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="cee8e-152">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-152">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="cee8e-153">Si el resumen de selecciones es correcto, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="cee8e-154">Cuando se completa la instalación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="cee8e-155">Para instalar IIS versión 7.0 en Windows Vista</span><span class="sxs-lookup"><span data-stu-id="cee8e-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1.  <span data-ttu-id="cee8e-156">Haga clic en Inicio y, a continuación, en Panel de control.</span><span class="sxs-lookup"><span data-stu-id="cee8e-156">Click Start, and then click Control Panel.</span></span>  
  
2.  <span data-ttu-id="cee8e-157">Seleccione el **programas** grupo.</span><span class="sxs-lookup"><span data-stu-id="cee8e-157">Select the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="cee8e-158">En **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="cee8e-159">El **User Account Control** se muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cee8e-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="cee8e-160">Haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-160">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="cee8e-161">El **las características de Windows** se muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cee8e-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="cee8e-162">Expanda el elemento con la etiqueta **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="cee8e-163">Expanda el elemento con la etiqueta **servicios World Wide Web**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="cee8e-164">Expanda el elemento con la etiqueta **Application Development Features**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="cee8e-165">Asegúrese de que los siguientes elementos están seleccionados:</span><span class="sxs-lookup"><span data-stu-id="cee8e-165">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="cee8e-166">**Extensibilidad de .NET**</span><span class="sxs-lookup"><span data-stu-id="cee8e-166">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="cee8e-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="cee8e-167">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="cee8e-168">**Extensiones ISAPI**</span><span class="sxs-lookup"><span data-stu-id="cee8e-168">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="cee8e-169">**Filtros ISAPI**</span><span class="sxs-lookup"><span data-stu-id="cee8e-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="cee8e-170">Expanda el elemento con la etiqueta **herramientas de administración Web**y, a continuación, seleccione **consola de administración de IIS**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="cee8e-171">En el elemento con la etiqueta **servicios World Wide Web**, expanda **características Http comunes**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="cee8e-172">Asegúrese de que **contenido estático** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cee8e-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="cee8e-173">En el elemento con la etiqueta **servicios World Wide Web**, expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="cee8e-174">Asegúrese de que **autenticación de Windows** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cee8e-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="cee8e-175">Expanda el elemento con la etiqueta **compatibilidad con la administración de IIS 6**y, a continuación, seleccione **herramientas de Scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="cee8e-176">Expanda el elemento con la etiqueta **Microsoft .NET Framework 3.0**y, a continuación, seleccione **activación Http de Windows Communication Foundation**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="cee8e-177">Haga clic en**Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-177">Click**OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="cee8e-178">Instalar la versión 6.0 de IIS en Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="cee8e-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1.  <span data-ttu-id="cee8e-179">De **Administre su servidor**, haga clic en **agregar o quitar un rol**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="cee8e-180">Seleccione **servidor de aplicaciones (IIS, ASP.NET)** desde el **rol de servidor** lista y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="cee8e-181">Seleccione **habilitar ASP.NET** casilla de verificación y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="cee8e-182">Si el resumen de selecciones es correcto, haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="cee8e-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="cee8e-183">Para instalar la versión 5.1 de IIS en Windows XP con Service Pack 2 y Service Pack 3 instalados</span><span class="sxs-lookup"><span data-stu-id="cee8e-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1.  <span data-ttu-id="cee8e-184">En el Panel de Control, haga clic en **agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="cee8e-185">En el **agregar o quitar programas** cuadro de diálogo, haga clic en **agregar o quitar componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="cee8e-186">En el **Asistente para componentes de Windows**, seleccione la **Internet Information Services (IIS)** casilla de verificación y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="cee8e-187">Si el **archivos necesarios** se muestra el cuadro de diálogo, inserte el disco de instalación de sistema operativo, vaya a la carpeta i386 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="cee8e-188">Cuando se completa la instalación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-188">When installation completes, click **Finish**.</span></span>  
  
6.  <span data-ttu-id="cee8e-189">Cerrar la **agregar o quitar programas** cuadro de diálogo y, a continuación, cierre **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="cee8e-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="cee8e-190">Para comprobar la instalación de IIS y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cee8e-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1.  <span data-ttu-id="cee8e-191">Guarde el archivo HTML encontrado al final de este tema en el directorio raíz \InetPub\wwwroot y denomínelo Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="cee8e-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2.  <span data-ttu-id="cee8e-192">Abra una ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="cee8e-192">Open a browser window.</span></span>  
  
3.  <span data-ttu-id="cee8e-193">Tipo `http://localhost/Default.aspx` en el cuadro Dirección y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="cee8e-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="cee8e-194">Debe aparecer una página web con el texto "Hello World".</span><span class="sxs-lookup"><span data-stu-id="cee8e-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cee8e-195">Cada vez que instale una nueva versión de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], debe volver a registrar aspnet_isapi como una extensión de servicio Web para IIS.</span><span class="sxs-lookup"><span data-stu-id="cee8e-195">Each time you install a new version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="cee8e-196">Para ello, ejecute el comando `aspnet_regiis –I –enable`.</span><span class="sxs-lookup"><span data-stu-id="cee8e-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="cee8e-197">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="cee8e-197">Sample Code</span></span>  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
