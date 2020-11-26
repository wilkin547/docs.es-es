---
title: Instrucciones de hospedaje Internet Information Services
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 151c5ba8dd79e8554e7d79fb5b8182740b0be18e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237695"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="638a6-102">Instrucciones de hospedaje Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="638a6-102">Internet Information Service Hosting Instructions</span></span>

<span data-ttu-id="638a6-103">Para ejecutar los ejemplos que son hospedados por Internet Information Services (IIS), debe asegurarse de que IIS está instalado correctamente y se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="638a6-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="638a6-104">Para instalar la versión 7.5 de IIS en Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="638a6-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="638a6-105">En **Administrador del servidor**, seleccione **roles.**</span><span class="sxs-lookup"><span data-stu-id="638a6-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="638a6-106">En **Resumen de roles**, haga clic en **Agregar roles**.</span><span class="sxs-lookup"><span data-stu-id="638a6-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="638a6-107">Haga clic en **siguiente** para mostrar el cuadro de diálogo **Seleccionar roles de servidor** .</span><span class="sxs-lookup"><span data-stu-id="638a6-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="638a6-108">Seleccione **servidor de aplicaciones** en la lista **roles** y, a continuación, haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="638a6-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="638a6-109">Active la casilla **servidor Web (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="638a6-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="638a6-110">Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar características necesarias**.</span><span class="sxs-lookup"><span data-stu-id="638a6-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="638a6-111">Haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="638a6-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="638a6-112">Expanda **herramientas de administración** y, a continuación, compatibilidad con la **Administración de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="638a6-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="638a6-113">Seleccione **herramientas de scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="638a6-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="638a6-114">Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar servicios de rol requeridos**.</span><span class="sxs-lookup"><span data-stu-id="638a6-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="638a6-115">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="638a6-115">Click **Next**.</span></span>  
  
6. <span data-ttu-id="638a6-116">Si el Resumen de selecciones es correcto, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="638a6-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="638a6-117">Cuando finalice la instalación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="638a6-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="638a6-118">Para instalar IIS versión 7.5 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="638a6-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1. <span data-ttu-id="638a6-119">Haga clic en **Inicio** y, a continuación, en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="638a6-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="638a6-120">Abra el grupo **programas** .</span><span class="sxs-lookup"><span data-stu-id="638a6-120">Open the **Programs** group.</span></span>  
  
3. <span data-ttu-id="638a6-121">En **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="638a6-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="638a6-122">Se muestra el cuadro de diálogo **control de cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="638a6-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="638a6-123">Haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="638a6-123">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="638a6-124">Se muestra el cuadro de diálogo **características de Windows** .</span><span class="sxs-lookup"><span data-stu-id="638a6-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="638a6-125">Expanda el elemento con la etiqueta **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="638a6-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="638a6-126">Expanda el elemento con la etiqueta **World Wide Web Servicios**.</span><span class="sxs-lookup"><span data-stu-id="638a6-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="638a6-127">Expanda el elemento con la etiqueta **características de desarrollo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="638a6-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="638a6-128">Asegúrese de que los siguientes elementos están seleccionados:</span><span class="sxs-lookup"><span data-stu-id="638a6-128">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="638a6-129">**Extensibilidad de .NET**</span><span class="sxs-lookup"><span data-stu-id="638a6-129">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="638a6-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="638a6-130">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="638a6-131">**Extensiones ISAPI**</span><span class="sxs-lookup"><span data-stu-id="638a6-131">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="638a6-132">**Filtros ISAPI**</span><span class="sxs-lookup"><span data-stu-id="638a6-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="638a6-133">En el elemento con la etiqueta **World Wide Web Servicios**, expanda **características http comunes**.</span><span class="sxs-lookup"><span data-stu-id="638a6-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="638a6-134">Asegúrese de que está seleccionado **contenido estático** .</span><span class="sxs-lookup"><span data-stu-id="638a6-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="638a6-135">En el elemento con la etiqueta **World Wide Web Servicios**, expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="638a6-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="638a6-136">Asegúrese de que la opción **autenticación de Windows** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="638a6-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="638a6-137">En el directorio **Internet Information Services** , expanda el elemento con la etiqueta **herramientas de administración web** y, a continuación, seleccione **consola de administración de IIS**.</span><span class="sxs-lookup"><span data-stu-id="638a6-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="638a6-138">Expanda el elemento con la etiqueta **compatibilidad de administración de IIS 6** y, a continuación, seleccione **herramientas de scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="638a6-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="638a6-139">En el directorio **Internet Information Services** , expanda el elemento con la etiqueta **Microsoft .NET Framework 3.5.1** y, a continuación, seleccione **Windows Communication Foundation activación http**.</span><span class="sxs-lookup"><span data-stu-id="638a6-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="638a6-140">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="638a6-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="638a6-141">Para instalar la versión de IIS 7.0 en Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="638a6-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1. <span data-ttu-id="638a6-142">En **Administrador del servidor**, seleccione **roles**.</span><span class="sxs-lookup"><span data-stu-id="638a6-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="638a6-143">En **Resumen de roles**, haga clic en **Agregar roles**.</span><span class="sxs-lookup"><span data-stu-id="638a6-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="638a6-144">Haga clic en **siguiente** para mostrar el cuadro de diálogo **Seleccionar roles de servidor** .</span><span class="sxs-lookup"><span data-stu-id="638a6-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="638a6-145">Seleccione **servidor de aplicaciones** en la lista **roles** y, a continuación, haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="638a6-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="638a6-146">Active la casilla **servidor Web (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="638a6-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="638a6-147">Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar características necesarias**.</span><span class="sxs-lookup"><span data-stu-id="638a6-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="638a6-148">Haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="638a6-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="638a6-149">Expanda **herramientas de administración** y, a continuación, compatibilidad con la **Administración de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="638a6-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="638a6-150">Seleccione **herramientas de scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="638a6-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="638a6-151">Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar servicios de rol requeridos**.</span><span class="sxs-lookup"><span data-stu-id="638a6-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="638a6-152">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="638a6-152">Click **Next**.</span></span>  
  
6. <span data-ttu-id="638a6-153">Si el Resumen de selecciones es correcto, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="638a6-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="638a6-154">Cuando finalice la instalación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="638a6-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="638a6-155">Para instalar IIS versión 7.0 en Windows Vista</span><span class="sxs-lookup"><span data-stu-id="638a6-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1. <span data-ttu-id="638a6-156">Haga clic en Inicio y, a continuación, en Panel de control.</span><span class="sxs-lookup"><span data-stu-id="638a6-156">Click Start, and then click Control Panel.</span></span>  
  
2. <span data-ttu-id="638a6-157">Seleccione el grupo **programas** .</span><span class="sxs-lookup"><span data-stu-id="638a6-157">Select the **Programs** group.</span></span>  
  
3. <span data-ttu-id="638a6-158">En **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="638a6-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="638a6-159">Se muestra el cuadro de diálogo **control de cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="638a6-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="638a6-160">Haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="638a6-160">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="638a6-161">Se muestra el cuadro de diálogo **características de Windows** .</span><span class="sxs-lookup"><span data-stu-id="638a6-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="638a6-162">Expanda el elemento con la etiqueta **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="638a6-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="638a6-163">Expanda el elemento con la etiqueta **World Wide Web Servicios**.</span><span class="sxs-lookup"><span data-stu-id="638a6-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="638a6-164">Expanda el elemento con la etiqueta **características de desarrollo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="638a6-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="638a6-165">Asegúrese de que los siguientes elementos están seleccionados:</span><span class="sxs-lookup"><span data-stu-id="638a6-165">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="638a6-166">**Extensibilidad de .NET**</span><span class="sxs-lookup"><span data-stu-id="638a6-166">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="638a6-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="638a6-167">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="638a6-168">**Extensiones ISAPI**</span><span class="sxs-lookup"><span data-stu-id="638a6-168">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="638a6-169">**Filtros ISAPI**</span><span class="sxs-lookup"><span data-stu-id="638a6-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="638a6-170">Expanda el elemento con la etiqueta **herramientas de administración web** y, a continuación, seleccione **consola de administración de IIS**.</span><span class="sxs-lookup"><span data-stu-id="638a6-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="638a6-171">En el elemento con la etiqueta **World Wide Web Servicios**, expanda **características http comunes**.</span><span class="sxs-lookup"><span data-stu-id="638a6-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="638a6-172">Asegúrese de que está seleccionado **contenido estático** .</span><span class="sxs-lookup"><span data-stu-id="638a6-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="638a6-173">En el elemento con la etiqueta **World Wide Web Servicios**, expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="638a6-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="638a6-174">Asegúrese de que la opción **autenticación de Windows** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="638a6-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="638a6-175">Expanda el elemento con la etiqueta **compatibilidad de administración de IIS 6** y, a continuación, seleccione **herramientas de scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="638a6-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="638a6-176">Expanda el elemento con la etiqueta **Microsoft .NET Framework 3,0** y, a continuación, seleccione **Windows Communication Foundation activación http**.</span><span class="sxs-lookup"><span data-stu-id="638a6-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="638a6-177">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="638a6-177">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="638a6-178">Instalar la versión 6.0 de IIS en Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="638a6-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1. <span data-ttu-id="638a6-179">En **administrar su servidor**, haga clic en **Agregar o quitar un rol** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="638a6-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2. <span data-ttu-id="638a6-180">Seleccione **servidor de aplicaciones (IIS, ASP.net)** en la lista **función de servidor** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="638a6-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="638a6-181">Active la casilla **habilitar ASP.net** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="638a6-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="638a6-182">Si el resumen de selecciones es correcto, haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="638a6-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="638a6-183">Para instalar la versión 5.1 de IIS en Windows XP con Service Pack 2 y Service Pack 3 instalados</span><span class="sxs-lookup"><span data-stu-id="638a6-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1. <span data-ttu-id="638a6-184">En el Panel de control, haga clic en **Agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="638a6-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2. <span data-ttu-id="638a6-185">En el cuadro de diálogo **Agregar o quitar programas**, haga clic en **Agregar o quitar componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="638a6-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3. <span data-ttu-id="638a6-186">En el **Asistente para componentes de Windows**, active la casilla **Internet Information Services (IIS)** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="638a6-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="638a6-187">Si aparece el cuadro de diálogo **archivos necesarios** , inserte el disco de instalación del sistema operativo, vaya a la carpeta i386 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="638a6-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="638a6-188">Cuando finalice la instalación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="638a6-188">When installation completes, click **Finish**.</span></span>  
  
6. <span data-ttu-id="638a6-189">Cierre el cuadro de diálogo **Agregar o quitar programas** y, a continuación, cierre el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="638a6-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="638a6-190">Para comprobar la instalación de IIS y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="638a6-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1. <span data-ttu-id="638a6-191">Guarde el archivo HTML encontrado al final de este tema en el directorio raíz \InetPub\wwwroot y denomínelo Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="638a6-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2. <span data-ttu-id="638a6-192">Abra una ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="638a6-192">Open a browser window.</span></span>  
  
3. <span data-ttu-id="638a6-193">Escriba `http://localhost/Default.aspx` en el cuadro Dirección y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="638a6-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="638a6-194">Debe aparecer una página web con el texto "Hello World".</span><span class="sxs-lookup"><span data-stu-id="638a6-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="638a6-195">Cada vez que instale una nueva versión de la .NET Framework, debe volver a registrar aspnet_isapi como una extensión de servicio web para IIS.</span><span class="sxs-lookup"><span data-stu-id="638a6-195">Each time you install a new version of the .NET Framework, you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="638a6-196">Para ello, ejecute el comando `aspnet_regiis –I –enable`.</span><span class="sxs-lookup"><span data-stu-id="638a6-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="638a6-197">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="638a6-197">Sample Code</span></span>  
  
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
