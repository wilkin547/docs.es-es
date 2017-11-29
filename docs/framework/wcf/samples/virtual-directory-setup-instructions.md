---
title: "Instrucciones de configuración del directorio virtual"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
caps.latest.revision: "36"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b727f391abfeb1112de1b6cde3ceb564d3860974
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="aa82c-102">Instrucciones de configuración del directorio virtual</span><span class="sxs-lookup"><span data-stu-id="aa82c-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="aa82c-103">Los ejemplos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] comparten un directorio virtual común denominado servicemodelsamples que está asignado a la carpeta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="aa82c-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa82c-104">%SystemDrive% acostumbra a ser C: o D:, según la ubicación de la unidad en que está instalado Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="aa82c-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="aa82c-105">Puede ejecutar los archivos Setupvroot.bat y Cleanupvroot.bat desde el [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) para crear el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="aa82c-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="aa82c-106">Si prefiere crear manualmente el directorio virtual, utilice los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="aa82c-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="aa82c-107">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="aa82c-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="aa82c-108">Para crear un directorio virtual en IIS 7.0 o 7.5</span><span class="sxs-lookup"><span data-stu-id="aa82c-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="aa82c-109">Desde el **iniciar** menú, haga clic en **ejecutar**, a continuación, escriba **inetmgr** para abrir el complemento MMC de servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="aa82c-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="aa82c-110">En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el **sitios** nodo.</span><span class="sxs-lookup"><span data-stu-id="aa82c-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3.  <span data-ttu-id="aa82c-111">Haga clic en **sitio Web predeterminado**y, a continuación, seleccione **Agregar aplicación** para abrir el **ventana Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4.  <span data-ttu-id="aa82c-112">En la ventana, escriba `servicemodelsamples` como alias para el directorio virtual que va a crear.</span><span class="sxs-lookup"><span data-stu-id="aa82c-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="aa82c-113">Cree el siguiente directorio: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="aa82c-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6.  <span data-ttu-id="aa82c-114">Especifique la ruta de acceso física a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="aa82c-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="aa82c-115">La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="aa82c-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7.  <span data-ttu-id="aa82c-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-116">Click **OK**.</span></span> <span data-ttu-id="aa82c-117">Ahora se crea la aplicación web para los ejemplos de WCF.</span><span class="sxs-lookup"><span data-stu-id="aa82c-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aa82c-118">Esta tarea solo se debe realizar una vez, porque todos los ejemplos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizan la misma aplicación web servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="aa82c-118">This task must be performed only once, because all of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aa82c-119">En esta documentación, el término `virtual directory` es sinónimo de `Web application`.</span><span class="sxs-lookup"><span data-stu-id="aa82c-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="aa82c-120">Además de crear el directorio virtual, también debe establecer sus propiedades para permitir que los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se ejecuten.</span><span class="sxs-lookup"><span data-stu-id="aa82c-120">In addition to creating the virtual directory, you must also set its properties to enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to run.</span></span> <span data-ttu-id="aa82c-121">Para obtener información más detallada, vea a continuación.</span><span class="sxs-lookup"><span data-stu-id="aa82c-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="aa82c-122">Para crear un directorio virtual en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="aa82c-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="aa82c-123">Abra una ventana de símbolo del sistema y escriba `start inetmgr` para abrir el complemento MMC de servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="aa82c-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="aa82c-124">En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el **sitios Web** nodo.</span><span class="sxs-lookup"><span data-stu-id="aa82c-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3.  <span data-ttu-id="aa82c-125">Haga clic en **sitio Web predeterminado** y seleccione **nuevo, el directorio Virtual** para abrir el Asistente para crear un directorio Virtual.</span><span class="sxs-lookup"><span data-stu-id="aa82c-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4.  <span data-ttu-id="aa82c-126">En el asistente, escriba `servicemodelsamples` como alias para el directorio virtual que va a crear.</span><span class="sxs-lookup"><span data-stu-id="aa82c-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="aa82c-127">Especifique la ruta de acceso a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="aa82c-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="aa82c-128">La mayoría de los ejemplos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="aa82c-128">Most of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples copy service executable files to this location when built.</span></span>  
  
6.  <span data-ttu-id="aa82c-129">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-129">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="aa82c-130">De forma predeterminada, las casillas siguientes están activadas:</span><span class="sxs-lookup"><span data-stu-id="aa82c-130">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="aa82c-131">**Lectura**</span><span class="sxs-lookup"><span data-stu-id="aa82c-131">**Read**</span></span>  
  
    -   <span data-ttu-id="aa82c-132">**Ejecutar secuencias de comandos (como ASP)**</span><span class="sxs-lookup"><span data-stu-id="aa82c-132">**Run scripts (such as ASP)**</span></span>  
  
8.  <span data-ttu-id="aa82c-133">Haga clic en **siguiente**y, a continuación, haga clic en **finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="aa82c-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aa82c-134">Esta tarea solo se debe realizar una vez, porque todos los ejemplos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizan el mismo directorio virtual servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="aa82c-134">This task must be performed only once because all of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="aa82c-135">Para establecer las propiedades de directorio virtual adicional en IIS 7.0 o 7.5</span><span class="sxs-lookup"><span data-stu-id="aa82c-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="aa82c-136">Haga clic en el nodo servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="aa82c-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="aa82c-137">Se muestran dos vistas en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="aa82c-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="aa82c-138">Seleccione **vista características** si aún no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="aa82c-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2.  <span data-ttu-id="aa82c-139">Haga doble clic en la entrada de **examen de directorios**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3.  <span data-ttu-id="aa82c-140">En el panel Acciones, seleccione la **habilitar** opción.</span><span class="sxs-lookup"><span data-stu-id="aa82c-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="aa82c-141">Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.</span><span class="sxs-lookup"><span data-stu-id="aa82c-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="aa82c-142">Finalmente, debe establecer las propiedades de seguridad de la carpeta servicemodelsamples para permitir que otros puedan obtener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="aa82c-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="aa82c-143">Para obtener información más detallada, vea a continuación.</span><span class="sxs-lookup"><span data-stu-id="aa82c-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="aa82c-144">Para establecer propiedades de directorio virtual adicionales en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="aa82c-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="aa82c-145">Haga clic en el nodo servicemodelsamples y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="aa82c-146">De forma predeterminada, las casillas siguientes están activadas:</span><span class="sxs-lookup"><span data-stu-id="aa82c-146">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="aa82c-147">**Lectura**</span><span class="sxs-lookup"><span data-stu-id="aa82c-147">**Read**</span></span>  
  
    -   <span data-ttu-id="aa82c-148">**Registrar visitas**</span><span class="sxs-lookup"><span data-stu-id="aa82c-148">**Log visits**</span></span>  
  
    -   <span data-ttu-id="aa82c-149">**Indizar este recurso**</span><span class="sxs-lookup"><span data-stu-id="aa82c-149">**Index this resource**</span></span>  
  
3.  <span data-ttu-id="aa82c-150">Seleccione el **examen de directorios** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="aa82c-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="aa82c-151">Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.</span><span class="sxs-lookup"><span data-stu-id="aa82c-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="aa82c-152">Para establecer propiedades de seguridad de la carpeta en IIS 7.0 o 7.5</span><span class="sxs-lookup"><span data-stu-id="aa82c-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="aa82c-153">Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="aa82c-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="aa82c-154">Haga clic en la carpeta servicemodelsamples y haga clic en **recurso compartido** o **compartir con**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3.  <span data-ttu-id="aa82c-155">Haga clic en la flecha hacia abajo a la izquierda de la **agregar** botón.</span><span class="sxs-lookup"><span data-stu-id="aa82c-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4.  <span data-ttu-id="aa82c-156">Seleccione el **buscar** entrada.</span><span class="sxs-lookup"><span data-stu-id="aa82c-156">Select the **Find** entry.</span></span> <span data-ttu-id="aa82c-157">El **Seleccionar usuarios o grupos** abre la ventana.</span><span class="sxs-lookup"><span data-stu-id="aa82c-157">The **Select Users or Groups** window opens.</span></span>  
  
5.  <span data-ttu-id="aa82c-158">Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-158">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="aa82c-159">Haga clic en **ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-159">Click **Locations**.</span></span> <span data-ttu-id="aa82c-160">El **ubicaciones** ventana está ahora abierta.</span><span class="sxs-lookup"><span data-stu-id="aa82c-160">The **Locations** window is now open.</span></span>  
  
7.  <span data-ttu-id="aa82c-161">Seleccione la entrada para el equipo que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="aa82c-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="aa82c-162">Es importante seleccionar el equipo local y no una entrada para cualquier dominio o red de la lista.</span><span class="sxs-lookup"><span data-stu-id="aa82c-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="aa82c-163">Después de haber seleccionado el equipo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-163">After you have selected the computer, click **OK**.</span></span>  
  
8.  <span data-ttu-id="aa82c-164">Haga clic en **Buscar ahora**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-164">Click **Find Now**.</span></span> <span data-ttu-id="aa82c-165">De este modo se rellenan los resultados de la búsqueda con objetos asociados al equipo local.</span><span class="sxs-lookup"><span data-stu-id="aa82c-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="aa82c-166">Buscar el **IIS_IUSRS** entrada en el **nombre (nombre distintivo relativo)** columna.</span><span class="sxs-lookup"><span data-stu-id="aa82c-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="aa82c-167">Seleccione esa entrada y haga clic en **Aceptar** cerrar esta ventana de resultados.</span><span class="sxs-lookup"><span data-stu-id="aa82c-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="aa82c-168">Haga clic en **Aceptar** para cerrar el **Seleccionar usuarios o grupos** ventana.</span><span class="sxs-lookup"><span data-stu-id="aa82c-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="aa82c-169">Haga clic en **recurso compartido** para conservar los cambios.</span><span class="sxs-lookup"><span data-stu-id="aa82c-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="aa82c-170">Una vez completados los cambios para habilitar el uso compartido, haga clic en **realiza** para cerrar el **uso compartido de archivos** ventana.</span><span class="sxs-lookup"><span data-stu-id="aa82c-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="aa82c-171">Para establecer propiedades de seguridad de la carpeta en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="aa82c-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="aa82c-172">Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="aa82c-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="aa82c-173">Haga clic en el **servicemodelsamples** carpeta y, a continuación, haga clic en **compartir y seguridad.**</span><span class="sxs-lookup"><span data-stu-id="aa82c-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3.  <span data-ttu-id="aa82c-174">Haga clic en la pestaña **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="aa82c-174">Click the **Security** tab.</span></span>  
  
4.  <span data-ttu-id="aa82c-175">Si usa IIS 6.0, en el **nombres de grupo o usuario** casilla de verificación si **cuenta de invitado para Internet** aparece.</span><span class="sxs-lookup"><span data-stu-id="aa82c-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="aa82c-176">Si no está en la lista:</span><span class="sxs-lookup"><span data-stu-id="aa82c-176">If it is not listed:</span></span>  
  
    1.  <span data-ttu-id="aa82c-177">Haga clic en **iniciar** y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="aa82c-178">Si no ve el **cuentas de usuario** icono, haga clic en **cambiar a vista por categorías**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3.  <span data-ttu-id="aa82c-179">Haga clic en el **cuentas de usuario** icono.</span><span class="sxs-lookup"><span data-stu-id="aa82c-179">Click the **User Accounts** icon.</span></span>  
  
    4.  <span data-ttu-id="aa82c-180">Bajo "o elija un icono del Panel de Control," haga clic en **cuentas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5.  <span data-ttu-id="aa82c-181">En el **cuentas de usuario** cuadro de diálogo, haga clic en el **avanzadas** ficha.</span><span class="sxs-lookup"><span data-stu-id="aa82c-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6.  <span data-ttu-id="aa82c-182">Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-182">Click **Advanced**.</span></span>  
  
    7.  <span data-ttu-id="aa82c-183">En el **usuarios y grupos locales** cuadro de diálogo, haga clic para expandir el **usuarios** carpeta.</span><span class="sxs-lookup"><span data-stu-id="aa82c-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8.  <span data-ttu-id="aa82c-184">En el panel derecho, haga doble clic en **cuenta de invitado para Internet**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="aa82c-185">En el **propiedades** cuadro de diálogo, copie el nombre se usa como la cuenta de invitado de Internet.</span><span class="sxs-lookup"><span data-stu-id="aa82c-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="aa82c-186">De forma predeterminada, el nombre comienza con "USR_" seguido por el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="aa82c-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="aa82c-187">Cerrar la **propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aa82c-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="aa82c-188">Cerrar la **usuarios y grupos locales** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aa82c-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="aa82c-189">Cerrar la **cuentas de usuario** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aa82c-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="aa82c-190">Cierre el otro **cuentas de usuario** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aa82c-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="aa82c-191">En el **servicemodelsamples propiedades** cuadro de diálogo, en la **seguridad** , haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="aa82c-192">Escriba el nombre del equipo seguido por una barra diagonal inversa, a continuación, pegue el nombre de la cuenta de usuario de Internet, por ejemplo, myMachineName\\% InternetGuestAccountName %</span><span class="sxs-lookup"><span data-stu-id="aa82c-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="aa82c-193">Haga clic en **comprobar nombres** para comprobar la adición.</span><span class="sxs-lookup"><span data-stu-id="aa82c-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="aa82c-194">Si es válido, el nombre está en mayúsculas y subrayado.</span><span class="sxs-lookup"><span data-stu-id="aa82c-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5.  <span data-ttu-id="aa82c-195">Para IIS 6.0, compruebe también que el servicio de red se muestra en el **nombres de grupo o usuario** cuadro.</span><span class="sxs-lookup"><span data-stu-id="aa82c-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="aa82c-196">Si el servicio de red no está en la lista:</span><span class="sxs-lookup"><span data-stu-id="aa82c-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1.  <span data-ttu-id="aa82c-197">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-197">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="aa82c-198">En el **Seleccionar usuarios o grupos** cuadro de diálogo, escriba el nombre del equipo seguido por una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="aa82c-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3.  <span data-ttu-id="aa82c-199">Tipo de **servicio** después de la barra diagonal inversa (sin espacio).</span><span class="sxs-lookup"><span data-stu-id="aa82c-199">Type **service** after the backslash (no space).</span></span>  
  
    4.  <span data-ttu-id="aa82c-200">Haga clic en **comprobar nombres**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-200">Click **Check names**.</span></span>  
  
    5.  <span data-ttu-id="aa82c-201">Si se encuentran varios nombres, seleccione **servicio de red** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6.  <span data-ttu-id="aa82c-202">Haga clic en **Aceptar** para cerrar el **Seleccionar usuarios o grupos** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aa82c-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6.  <span data-ttu-id="aa82c-203">Si usas Windows XP SP2 con IIS 5.1, compruebe que cuenta de invitado para Internet y ASPNET aparecen en la **nombres de grupo o usuario** cuadro.</span><span class="sxs-lookup"><span data-stu-id="aa82c-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="aa82c-204">Tenga en cuenta que el usuario ASPNET puede ser un miembro de los integrados **usuarios** grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aa82c-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="aa82c-205">Si es así, entonces si el **usuarios** grupo aparece en el cuadro de diálogo, no es necesario agregarlo como un elemento independiente a la lista de usuarios permitidos.</span><span class="sxs-lookup"><span data-stu-id="aa82c-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="aa82c-206">Para comprobar si ASPNET forma parte de la **usuarios** grupo de seguridad:</span><span class="sxs-lookup"><span data-stu-id="aa82c-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1.  <span data-ttu-id="aa82c-207">En el **iniciar** menú, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="aa82c-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="aa82c-208">Haga clic en el **cuentas de usuario** icono.</span><span class="sxs-lookup"><span data-stu-id="aa82c-208">Click the **User Accounts** icon.</span></span>  
  
    3.  <span data-ttu-id="aa82c-209">En el **grupo** columna, compruebe que el valor de **ASPNET** es "Users".</span><span class="sxs-lookup"><span data-stu-id="aa82c-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa82c-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa82c-210">See Also</span></span>  
 [<span data-ttu-id="aa82c-211">Instrucciones de hospedaje de Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="aa82c-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
