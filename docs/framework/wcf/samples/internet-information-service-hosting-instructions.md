---
description: 'Más información acerca de: instrucciones de hospedaje de Internet Information Services'
title: Instrucciones de hospedaje Internet Information Services
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 51f5230ecbb8eaf4a909c5c09366680b8c555165
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726382"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="9dc45-103">Instrucciones de hospedaje Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="9dc45-103">Internet Information Service Hosting Instructions</span></span>

<span data-ttu-id="9dc45-104">Para ejecutar los ejemplos que son hospedados por Internet Information Services (IIS), debe asegurarse de que IIS está instalado correctamente y se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="9dc45-104">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="9dc45-105">Para instalar la versión 7.5 de IIS en Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9dc45-105">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="9dc45-106">En **Administrador del servidor**, seleccione **roles.**</span><span class="sxs-lookup"><span data-stu-id="9dc45-106">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="9dc45-107">En **Resumen de roles**, haga clic en **Agregar roles**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-107">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="9dc45-108">Haga clic en **siguiente** para mostrar el cuadro de diálogo **Seleccionar roles de servidor** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-108">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="9dc45-109">Seleccione **servidor de aplicaciones** en la lista **roles** y, a continuación, haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9dc45-109">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="9dc45-110">Active la casilla **servidor Web (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-110">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="9dc45-111">Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar características necesarias**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-111">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="9dc45-112">Haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="9dc45-112">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="9dc45-113">Expanda **herramientas de administración** y, a continuación, compatibilidad con la **Administración de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-113">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="9dc45-114">Seleccione **herramientas de scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-114">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="9dc45-115">Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar servicios de rol requeridos**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-115">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="9dc45-116">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-116">Click **Next**.</span></span>  
  
6. <span data-ttu-id="9dc45-117">Si el Resumen de selecciones es correcto, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-117">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="9dc45-118">Cuando finalice la instalación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-118">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="9dc45-119">Para instalar IIS versión 7.5 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="9dc45-119">To install IIS version 7.5 on Windows 7</span></span>  
  
1. <span data-ttu-id="9dc45-120">Haga clic en **Inicio** y, a continuación, en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-120">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="9dc45-121">Abra el grupo **programas** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-121">Open the **Programs** group.</span></span>  
  
3. <span data-ttu-id="9dc45-122">En **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-122">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="9dc45-123">Se muestra el cuadro de diálogo **control de cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-123">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="9dc45-124">Haga clic en **Continue**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-124">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="9dc45-125">Se muestra el cuadro de diálogo **características de Windows** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-125">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="9dc45-126">Expanda el elemento con la etiqueta **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-126">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="9dc45-127">Expanda el elemento con la etiqueta **World Wide Web Servicios**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-127">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="9dc45-128">Expanda el elemento con la etiqueta **características de desarrollo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-128">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="9dc45-129">Asegúrese de que los siguientes elementos están seleccionados:</span><span class="sxs-lookup"><span data-stu-id="9dc45-129">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="9dc45-130">**Extensibilidad de .NET**</span><span class="sxs-lookup"><span data-stu-id="9dc45-130">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="9dc45-131">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="9dc45-131">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="9dc45-132">**Extensiones ISAPI**</span><span class="sxs-lookup"><span data-stu-id="9dc45-132">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="9dc45-133">**Filtros ISAPI**</span><span class="sxs-lookup"><span data-stu-id="9dc45-133">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="9dc45-134">En el elemento con la etiqueta **World Wide Web Servicios**, expanda **características http comunes**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-134">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="9dc45-135">Asegúrese de que está seleccionado **contenido estático** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-135">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="9dc45-136">En el elemento con la etiqueta **World Wide Web Servicios**, expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-136">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="9dc45-137">Asegúrese de que la opción **autenticación de Windows** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dc45-137">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="9dc45-138">En el directorio **Internet Information Services** , expanda el elemento con la etiqueta **herramientas de administración web** y, a continuación, seleccione **consola de administración de IIS**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-138">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="9dc45-139">Expanda el elemento con la etiqueta **compatibilidad de administración de IIS 6** y, a continuación, seleccione **herramientas de scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-139">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="9dc45-140">En el directorio **Internet Information Services** , expanda el elemento con la etiqueta **Microsoft .NET Framework 3.5.1** y, a continuación, seleccione **Windows Communication Foundation activación http**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-140">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="9dc45-141">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-141">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="9dc45-142">Para instalar la versión de IIS 7.0 en Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="9dc45-142">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1. <span data-ttu-id="9dc45-143">En **Administrador del servidor**, seleccione **roles**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-143">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="9dc45-144">En **Resumen de roles**, haga clic en **Agregar roles**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-144">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="9dc45-145">Haga clic en **siguiente** para mostrar el cuadro de diálogo **Seleccionar roles de servidor** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-145">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="9dc45-146">Seleccione **servidor de aplicaciones** en la lista **roles** y, a continuación, haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9dc45-146">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="9dc45-147">Active la casilla **servidor Web (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-147">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="9dc45-148">Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar características necesarias**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-148">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="9dc45-149">Haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="9dc45-149">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="9dc45-150">Expanda **herramientas de administración** y, a continuación, compatibilidad con la **Administración de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-150">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="9dc45-151">Seleccione **herramientas de scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-151">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="9dc45-152">Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar servicios de rol requeridos**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-152">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="9dc45-153">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-153">Click **Next**.</span></span>  
  
6. <span data-ttu-id="9dc45-154">Si el Resumen de selecciones es correcto, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-154">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="9dc45-155">Cuando finalice la instalación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-155">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="9dc45-156">Para instalar IIS versión 7.0 en Windows Vista</span><span class="sxs-lookup"><span data-stu-id="9dc45-156">To install IIS version 7.0 on Windows Vista</span></span>  
  
1. <span data-ttu-id="9dc45-157">Haga clic en Inicio y, a continuación, en Panel de control.</span><span class="sxs-lookup"><span data-stu-id="9dc45-157">Click Start, and then click Control Panel.</span></span>  
  
2. <span data-ttu-id="9dc45-158">Seleccione el grupo **programas** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-158">Select the **Programs** group.</span></span>  
  
3. <span data-ttu-id="9dc45-159">En **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-159">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="9dc45-160">Se muestra el cuadro de diálogo **control de cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-160">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="9dc45-161">Haga clic en **Continue**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-161">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="9dc45-162">Se muestra el cuadro de diálogo **características de Windows** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-162">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="9dc45-163">Expanda el elemento con la etiqueta **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-163">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="9dc45-164">Expanda el elemento con la etiqueta **World Wide Web Servicios**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-164">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="9dc45-165">Expanda el elemento con la etiqueta **características de desarrollo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-165">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="9dc45-166">Asegúrese de que los siguientes elementos están seleccionados:</span><span class="sxs-lookup"><span data-stu-id="9dc45-166">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="9dc45-167">**Extensibilidad de .NET**</span><span class="sxs-lookup"><span data-stu-id="9dc45-167">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="9dc45-168">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="9dc45-168">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="9dc45-169">**Extensiones ISAPI**</span><span class="sxs-lookup"><span data-stu-id="9dc45-169">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="9dc45-170">**Filtros ISAPI**</span><span class="sxs-lookup"><span data-stu-id="9dc45-170">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="9dc45-171">Expanda el elemento con la etiqueta **herramientas de administración web** y, a continuación, seleccione **consola de administración de IIS**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-171">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="9dc45-172">En el elemento con la etiqueta **World Wide Web Servicios**, expanda **características http comunes**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-172">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="9dc45-173">Asegúrese de que está seleccionado **contenido estático** .</span><span class="sxs-lookup"><span data-stu-id="9dc45-173">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="9dc45-174">En el elemento con la etiqueta **World Wide Web Servicios**, expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-174">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="9dc45-175">Asegúrese de que la opción **autenticación de Windows** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dc45-175">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="9dc45-176">Expanda el elemento con la etiqueta **compatibilidad de administración de IIS 6** y, a continuación, seleccione **herramientas de scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-176">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="9dc45-177">Expanda el elemento con la etiqueta **Microsoft .NET Framework 3,0** y, a continuación, seleccione **Windows Communication Foundation activación http**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-177">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="9dc45-178">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-178">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="9dc45-179">Instalar la versión 6.0 de IIS en Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="9dc45-179">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1. <span data-ttu-id="9dc45-180">En **administrar su servidor**, haga clic en **Agregar o quitar un rol** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-180">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2. <span data-ttu-id="9dc45-181">Seleccione **servidor de aplicaciones (IIS, ASP.net)** en la lista **función de servidor** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-181">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="9dc45-182">Active la casilla **habilitar ASP.net** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-182">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="9dc45-183">Si el resumen de selecciones es correcto, haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="9dc45-183">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="9dc45-184">Para instalar la versión 5.1 de IIS en Windows XP con Service Pack 2 y Service Pack 3 instalados</span><span class="sxs-lookup"><span data-stu-id="9dc45-184">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1. <span data-ttu-id="9dc45-185">En el Panel de control, haga clic en **Agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-185">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2. <span data-ttu-id="9dc45-186">En el cuadro de diálogo **Agregar o quitar programas**, haga clic en **Agregar o quitar componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-186">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3. <span data-ttu-id="9dc45-187">En el **Asistente para componentes de Windows**, active la casilla **Internet Information Services (IIS)** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-187">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="9dc45-188">Si aparece el cuadro de diálogo **archivos necesarios** , inserte el disco de instalación del sistema operativo, vaya a la carpeta i386 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-188">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="9dc45-189">Cuando finalice la instalación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-189">When installation completes, click **Finish**.</span></span>  
  
6. <span data-ttu-id="9dc45-190">Cierre el cuadro de diálogo **Agregar o quitar programas** y, a continuación, cierre el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="9dc45-190">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="9dc45-191">Para comprobar la instalación de IIS y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9dc45-191">To verify the installation of IIS and ASP.NET</span></span>  
  
1. <span data-ttu-id="9dc45-192">Guarde el archivo HTML encontrado al final de este tema en el directorio raíz \InetPub\wwwroot y denomínelo Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="9dc45-192">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2. <span data-ttu-id="9dc45-193">Abra una ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="9dc45-193">Open a browser window.</span></span>  
  
3. <span data-ttu-id="9dc45-194">Escriba `http://localhost/Default.aspx` en el cuadro Dirección y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="9dc45-194">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="9dc45-195">Debe aparecer una página web con el texto "Hello World".</span><span class="sxs-lookup"><span data-stu-id="9dc45-195">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9dc45-196">Cada vez que instale una nueva versión de la .NET Framework, debe volver a registrar aspnet_isapi como una extensión de servicio web para IIS.</span><span class="sxs-lookup"><span data-stu-id="9dc45-196">Each time you install a new version of the .NET Framework, you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="9dc45-197">Para ello, ejecute el comando `aspnet_regiis –I –enable`.</span><span class="sxs-lookup"><span data-stu-id="9dc45-197">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="9dc45-198">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9dc45-198">Sample Code</span></span>  
  
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
