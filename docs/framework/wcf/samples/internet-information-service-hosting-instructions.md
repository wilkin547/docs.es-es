---
title: Instrucciones de hospedaje Internet Information Services
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 303fe47df987901b09cee8cc4292f12bcda2b74d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47204040"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="da4d0-102">Instrucciones de hospedaje Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="da4d0-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="da4d0-103">Para ejecutar los ejemplos que son hospedados por Internet Information Services (IIS), debe asegurarse de que IIS está instalado correctamente y se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="da4d0-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="da4d0-104">Para instalar la versión 7.5 de IIS en Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="da4d0-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="da4d0-105">Desde **administrador del servidor**, seleccione **Roles.**</span><span class="sxs-lookup"><span data-stu-id="da4d0-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="da4d0-106">En **resumen de funciones**, haga clic en **agregar Roles**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="da4d0-107">Haga clic en **siguiente** para mostrar el **seleccionar Roles de servidor** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="da4d0-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="da4d0-108">Seleccione **Application Server** desde el **Roles** lista y, a continuación, haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el Rol de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="da4d0-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="da4d0-109">Seleccione el **servidor Web (IIS)** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="da4d0-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="da4d0-110">Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar características requeridas**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="da4d0-111">Haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el rol de servidor Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="da4d0-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="da4d0-112">Expanda **las herramientas de administración**y, a continuación, expanda **compatibilidad con la administración de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="da4d0-113">Seleccione **IIS herramientas de Scripting 6**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="da4d0-114">Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar servicios de rol requeridos**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="da4d0-115">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-115">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="da4d0-116">Si el resumen de selecciones es correcto, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="da4d0-117">Cuando se completa la instalación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="da4d0-118">Para instalar IIS versión 7.5 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="da4d0-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1.  <span data-ttu-id="da4d0-119">Haga clic en **iniciar**y, a continuación, haga clic en **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="da4d0-120">Abra el **programas** grupo.</span><span class="sxs-lookup"><span data-stu-id="da4d0-120">Open the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="da4d0-121">En **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="da4d0-122">El **User Account Control** muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="da4d0-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="da4d0-123">Haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-123">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="da4d0-124">El **características de Windows** muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="da4d0-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="da4d0-125">Expanda el elemento con la etiqueta **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="da4d0-126">Expanda el elemento con la etiqueta **servicios World Wide Web**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="da4d0-127">Expanda el elemento con la etiqueta **Application Development Features**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="da4d0-128">Asegúrese de que los siguientes elementos están seleccionados:</span><span class="sxs-lookup"><span data-stu-id="da4d0-128">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="da4d0-129">**Extensibilidad de .NET**</span><span class="sxs-lookup"><span data-stu-id="da4d0-129">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="da4d0-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="da4d0-130">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="da4d0-131">**Extensiones ISAPI**</span><span class="sxs-lookup"><span data-stu-id="da4d0-131">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="da4d0-132">**Filtros ISAPI**</span><span class="sxs-lookup"><span data-stu-id="da4d0-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="da4d0-133">En el elemento con la etiqueta **servicios World Wide Web**, expanda **características Http comunes**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="da4d0-134">Asegúrese de que **contenido estático** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="da4d0-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="da4d0-135">En el elemento con la etiqueta **servicios World Wide Web**, expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="da4d0-136">Asegúrese de que **Windows autenticación** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="da4d0-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="da4d0-137">En el **Internet Information Services** directory, expanda el elemento con la etiqueta **herramientas de administración Web**y, a continuación, seleccione **consola de administración IIS**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="da4d0-138">Expanda el elemento con la etiqueta **compatibilidad con la administración de IIS 6**y, a continuación, seleccione **herramientas de Scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="da4d0-139">En el **Internet Information Services** directory, expanda el elemento con la etiqueta **Microsoft .NET Framework 3.5.1**y, a continuación, seleccione **activación Http de Windows Communication Foundation**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="da4d0-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="da4d0-141">Para instalar la versión de IIS 7.0 en Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="da4d0-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="da4d0-142">Desde **administrador del servidor**, seleccione **Roles**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="da4d0-143">En **resumen de funciones**, haga clic en **agregar Roles**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="da4d0-144">Haga clic en **siguiente** para mostrar el **seleccionar Roles de servidor** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="da4d0-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="da4d0-145">Seleccione **Application Server** desde el **Roles** lista y, a continuación, haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el Rol de servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="da4d0-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="da4d0-146">Seleccione **servidor Web (IIS)** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="da4d0-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="da4d0-147">Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar características requeridas**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="da4d0-148">Haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el rol de servidor Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="da4d0-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="da4d0-149">Expanda **las herramientas de administración**y, a continuación, expanda **compatibilidad con la administración de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="da4d0-150">Seleccione **IIS herramientas de Scripting 6**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="da4d0-151">Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar servicios de rol requeridos**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="da4d0-152">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-152">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="da4d0-153">Si el resumen de selecciones es correcto, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="da4d0-154">Cuando se completa la instalación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="da4d0-155">Para instalar IIS versión 7.0 en Windows Vista</span><span class="sxs-lookup"><span data-stu-id="da4d0-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1.  <span data-ttu-id="da4d0-156">Haga clic en Inicio y, a continuación, en Panel de control.</span><span class="sxs-lookup"><span data-stu-id="da4d0-156">Click Start, and then click Control Panel.</span></span>  
  
2.  <span data-ttu-id="da4d0-157">Seleccione el **programas** grupo.</span><span class="sxs-lookup"><span data-stu-id="da4d0-157">Select the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="da4d0-158">En **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="da4d0-159">El **User Account Control** muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="da4d0-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="da4d0-160">Haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-160">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="da4d0-161">El **características de Windows** muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="da4d0-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="da4d0-162">Expanda el elemento con la etiqueta **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="da4d0-163">Expanda el elemento con la etiqueta **servicios World Wide Web**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="da4d0-164">Expanda el elemento con la etiqueta **Application Development Features**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="da4d0-165">Asegúrese de que los siguientes elementos están seleccionados:</span><span class="sxs-lookup"><span data-stu-id="da4d0-165">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="da4d0-166">**Extensibilidad de .NET**</span><span class="sxs-lookup"><span data-stu-id="da4d0-166">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="da4d0-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="da4d0-167">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="da4d0-168">**Extensiones ISAPI**</span><span class="sxs-lookup"><span data-stu-id="da4d0-168">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="da4d0-169">**Filtros ISAPI**</span><span class="sxs-lookup"><span data-stu-id="da4d0-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="da4d0-170">Expanda el elemento con la etiqueta **herramientas de administración Web**y, a continuación, seleccione **consola de administración IIS**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="da4d0-171">En el elemento con la etiqueta **servicios World Wide Web**, expanda **características Http comunes**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="da4d0-172">Asegúrese de que **contenido estático** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="da4d0-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="da4d0-173">En el elemento con la etiqueta **servicios World Wide Web**, expanda **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="da4d0-174">Asegúrese de que **Windows autenticación** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="da4d0-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="da4d0-175">Expanda el elemento con la etiqueta **compatibilidad con la administración de IIS 6**y, a continuación, seleccione **herramientas de Scripting de IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="da4d0-176">Expanda el elemento con la etiqueta **Microsoft .NET Framework 3.0**y, a continuación, seleccione **activación Http de Windows Communication Foundation**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="da4d0-177">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-177">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="da4d0-178">Instalar la versión 6.0 de IIS en Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="da4d0-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1.  <span data-ttu-id="da4d0-179">Desde **Administre su servidor**, haga clic en **agregar o quitar una función**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="da4d0-180">Seleccione **servidor de aplicaciones (IIS, ASP.NET)** desde el **rol de servidor** lista y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="da4d0-181">Seleccione **habilitar ASP.NET** casilla de verificación y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="da4d0-182">Si el resumen de selecciones es correcto, haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="da4d0-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="da4d0-183">Para instalar la versión 5.1 de IIS en Windows XP con Service Pack 2 y Service Pack 3 instalados</span><span class="sxs-lookup"><span data-stu-id="da4d0-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1.  <span data-ttu-id="da4d0-184">En el Panel de Control, haga clic en **agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="da4d0-185">En el **agregar o quitar programas** cuadro de diálogo, haga clic en **agregar o quitar componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="da4d0-186">En el **Asistente para componentes de Windows**, seleccione el **Internet Information Services (IIS)** casilla de verificación y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="da4d0-187">Si el **archivos necesarios** se muestra el cuadro de diálogo, inserte el disco de instalación de sistema operativo, vaya a la carpeta i386 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="da4d0-188">Cuando se completa la instalación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-188">When installation completes, click **Finish**.</span></span>  
  
6.  <span data-ttu-id="da4d0-189">Cierre el **agregar o quitar programas** cuadro de diálogo y, a continuación, cierre **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="da4d0-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="da4d0-190">Para comprobar la instalación de IIS y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="da4d0-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1.  <span data-ttu-id="da4d0-191">Guarde el archivo HTML encontrado al final de este tema en el directorio raíz \InetPub\wwwroot y denomínelo Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="da4d0-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2.  <span data-ttu-id="da4d0-192">Abra una ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="da4d0-192">Open a browser window.</span></span>  
  
3.  <span data-ttu-id="da4d0-193">Tipo `http://localhost/Default.aspx` en el cuadro Dirección y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="da4d0-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="da4d0-194">Debe aparecer una página web con el texto "Hello World".</span><span class="sxs-lookup"><span data-stu-id="da4d0-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da4d0-195">Cada vez que instale una nueva versión de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], debe volver a registrar aspnet_isapi como una extensión de servicio Web para IIS.</span><span class="sxs-lookup"><span data-stu-id="da4d0-195">Each time you install a new version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="da4d0-196">Para ello, ejecute el comando `aspnet_regiis –I –enable`.</span><span class="sxs-lookup"><span data-stu-id="da4d0-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="da4d0-197">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="da4d0-197">Sample Code</span></span>  
  
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
