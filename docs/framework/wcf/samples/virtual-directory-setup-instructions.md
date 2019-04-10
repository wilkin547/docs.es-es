---
title: Instrucciones de configuración del directorio virtual
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 7999a040dc14d75a34b75f320982dd3118eae670
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225591"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="7b302-102">Instrucciones de configuración del directorio virtual</span><span class="sxs-lookup"><span data-stu-id="7b302-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="7b302-103">Los ejemplos de Windows Communication Foundation (WCF) están diseñados para compartir un directorio virtual común denominado servicemodelsamples que está asignado a la carpeta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7b302-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b302-104">%SystemDrive% acostumbra a ser C: o D:, según la ubicación de la unidad en que está instalado Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="7b302-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="7b302-105">Puede ejecutar los archivos Setupvroot.bat y Cleanupvroot.bat desde el [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) para crear el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="7b302-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="7b302-106">Si prefiere crear manualmente el directorio virtual, utilice los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7b302-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="7b302-107">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7b302-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="7b302-108">Para crear un directorio virtual en IIS 7.0 o 7.5</span><span class="sxs-lookup"><span data-stu-id="7b302-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="7b302-109">Desde el **iniciar** menú, haga clic en **ejecutar**, a continuación, escriba **inetmgr** para abrir el complemento MMC de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="7b302-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="7b302-110">En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el **sitios** nodo.</span><span class="sxs-lookup"><span data-stu-id="7b302-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3.  <span data-ttu-id="7b302-111">Haga clic en **sitio Web predeterminado**y, a continuación, seleccione **Agregar aplicación** para abrir el **ventana Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="7b302-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4.  <span data-ttu-id="7b302-112">En la ventana, escriba `servicemodelsamples` como alias para el directorio virtual que está creando.</span><span class="sxs-lookup"><span data-stu-id="7b302-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="7b302-113">Cree el siguiente directorio: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="7b302-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6.  <span data-ttu-id="7b302-114">Especifique la ruta de acceso física a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7b302-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="7b302-115">La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="7b302-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7.  <span data-ttu-id="7b302-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b302-116">Click **OK**.</span></span> <span data-ttu-id="7b302-117">Ahora se crea la aplicación web para los ejemplos de WCF.</span><span class="sxs-lookup"><span data-stu-id="7b302-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7b302-118">Esta tarea debe realizarse una sola vez, porque todos los ejemplos WCF usan la misma aplicación Web servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7b302-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7b302-119">En esta documentación, el término `virtual directory` es sinónimo de `Web application`.</span><span class="sxs-lookup"><span data-stu-id="7b302-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="7b302-120">Además de crear el directorio virtual, también debe establecer sus propiedades para permitir que se ejecuten los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="7b302-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="7b302-121">Para obtener información más detallada, vea a continuación.</span><span class="sxs-lookup"><span data-stu-id="7b302-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="7b302-122">Para crear un directorio virtual en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="7b302-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="7b302-123">Abra una ventana de símbolo del sistema y escriba `start inetmgr` para abrir el complemento MMC de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="7b302-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="7b302-124">En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el **sitios Web** nodo.</span><span class="sxs-lookup"><span data-stu-id="7b302-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3.  <span data-ttu-id="7b302-125">Haga clic en **sitio Web predeterminado** y seleccione **nuevo, el directorio Virtual** para abrir el Asistente para crear un directorio Virtual.</span><span class="sxs-lookup"><span data-stu-id="7b302-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4.  <span data-ttu-id="7b302-126">En el asistente, escriba `servicemodelsamples` como alias para el directorio virtual que está creando.</span><span class="sxs-lookup"><span data-stu-id="7b302-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="7b302-127">Especifique la ruta de acceso a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7b302-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="7b302-128">La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="7b302-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6.  <span data-ttu-id="7b302-129">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7b302-129">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="7b302-130">De forma predeterminada, las casillas siguientes están activadas:</span><span class="sxs-lookup"><span data-stu-id="7b302-130">By default, the following check boxes are selected:</span></span>  
  
    -   **<span data-ttu-id="7b302-131">Leer</span><span class="sxs-lookup"><span data-stu-id="7b302-131">Read</span></span>**  
  
    -   **<span data-ttu-id="7b302-132">Ejecutar scripts (como ASP)</span><span class="sxs-lookup"><span data-stu-id="7b302-132">Run scripts (such as ASP)</span></span>**  
  
8.  <span data-ttu-id="7b302-133">Haga clic en **siguiente**y, a continuación, haga clic en **finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="7b302-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7b302-134">Esta tarea debe realizarse una sola vez porque todos los ejemplos WCF usan el mismo directorio virtual servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7b302-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="7b302-135">Para establecer las propiedades del directorio virtual adicionales en IIS 7.0 o 7.5</span><span class="sxs-lookup"><span data-stu-id="7b302-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="7b302-136">Haga clic en el nodo servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7b302-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="7b302-137">Se muestran dos vistas en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="7b302-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="7b302-138">Seleccione **vista características** si aún no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7b302-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2.  <span data-ttu-id="7b302-139">Haga doble clic en la entrada de **examen de directorios**.</span><span class="sxs-lookup"><span data-stu-id="7b302-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3.  <span data-ttu-id="7b302-140">En el panel Acciones, seleccione el **habilitar** opción.</span><span class="sxs-lookup"><span data-stu-id="7b302-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="7b302-141">Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.</span><span class="sxs-lookup"><span data-stu-id="7b302-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="7b302-142">Finalmente, debe establecer las propiedades de seguridad de la carpeta servicemodelsamples para permitir que otros puedan obtener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="7b302-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="7b302-143">Para obtener información más detallada, vea a continuación.</span><span class="sxs-lookup"><span data-stu-id="7b302-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="7b302-144">Para establecer propiedades de directorio virtual adicionales en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="7b302-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="7b302-145">Haga clic en el nodo servicemodelsamples y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7b302-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7b302-146">De forma predeterminada, las casillas siguientes están activadas:</span><span class="sxs-lookup"><span data-stu-id="7b302-146">By default, the following check boxes are selected:</span></span>  
  
    -   **<span data-ttu-id="7b302-147">Leer</span><span class="sxs-lookup"><span data-stu-id="7b302-147">Read</span></span>**  
  
    -   **<span data-ttu-id="7b302-148">Registrar visitas</span><span class="sxs-lookup"><span data-stu-id="7b302-148">Log visits</span></span>**  
  
    -   **<span data-ttu-id="7b302-149">Indizar este recurso</span><span class="sxs-lookup"><span data-stu-id="7b302-149">Index this resource</span></span>**  
  
3.  <span data-ttu-id="7b302-150">Seleccione el **examen de directorios** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="7b302-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="7b302-151">Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.</span><span class="sxs-lookup"><span data-stu-id="7b302-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="7b302-152">Para establecer las propiedades de seguridad de la carpeta en IIS 7.0 o 7.5</span><span class="sxs-lookup"><span data-stu-id="7b302-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="7b302-153">Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7b302-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="7b302-154">Haga clic en la carpeta servicemodelsamples y haga clic en **Share** o **compartir con**.</span><span class="sxs-lookup"><span data-stu-id="7b302-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3.  <span data-ttu-id="7b302-155">Haga clic en la flecha hacia abajo a la izquierda de la **agregar** botón.</span><span class="sxs-lookup"><span data-stu-id="7b302-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4.  <span data-ttu-id="7b302-156">Seleccione el **buscar** entrada.</span><span class="sxs-lookup"><span data-stu-id="7b302-156">Select the **Find** entry.</span></span> <span data-ttu-id="7b302-157">El **Seleccionar usuarios o grupos** abre la ventana.</span><span class="sxs-lookup"><span data-stu-id="7b302-157">The **Select Users or Groups** window opens.</span></span>  
  
5.  <span data-ttu-id="7b302-158">Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="7b302-158">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="7b302-159">Haga clic en **ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="7b302-159">Click **Locations**.</span></span> <span data-ttu-id="7b302-160">El **ubicaciones** ahora está abierta la ventana.</span><span class="sxs-lookup"><span data-stu-id="7b302-160">The **Locations** window is now open.</span></span>  
  
7.  <span data-ttu-id="7b302-161">Seleccione la entrada para el equipo que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="7b302-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="7b302-162">Es importante seleccionar el equipo local y no una entrada para cualquier dominio o red de la lista.</span><span class="sxs-lookup"><span data-stu-id="7b302-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="7b302-163">Después de haber seleccionado el equipo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b302-163">After you have selected the computer, click **OK**.</span></span>  
  
8.  <span data-ttu-id="7b302-164">Haga clic en **Buscar ahora**.</span><span class="sxs-lookup"><span data-stu-id="7b302-164">Click **Find Now**.</span></span> <span data-ttu-id="7b302-165">De este modo se rellenan los resultados de la búsqueda con objetos asociados al equipo local.</span><span class="sxs-lookup"><span data-stu-id="7b302-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="7b302-166">Buscar el **IIS_IUSRS** entrada en el **nombre (nombre distintivo relativo)** columna.</span><span class="sxs-lookup"><span data-stu-id="7b302-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="7b302-167">Seleccione esa entrada y haga clic en **Aceptar** cerrar esta ventana de resultados.</span><span class="sxs-lookup"><span data-stu-id="7b302-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="7b302-168">Haga clic en **Aceptar** para cerrar el **Seleccionar usuarios o grupos** ventana.</span><span class="sxs-lookup"><span data-stu-id="7b302-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="7b302-169">Haga clic en **Share** para conservar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7b302-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="7b302-170">Una vez completados los cambios para habilitar el uso compartido, haga clic en **realiza** para cerrar el **uso compartido de archivos** ventana.</span><span class="sxs-lookup"><span data-stu-id="7b302-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="7b302-171">Para establecer propiedades de seguridad de la carpeta en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="7b302-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="7b302-172">Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7b302-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="7b302-173">Haga clic en el **servicemodelsamples** carpeta y, a continuación, haga clic en **compartir y seguridad.**</span><span class="sxs-lookup"><span data-stu-id="7b302-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3.  <span data-ttu-id="7b302-174">Haga clic en la pestaña **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="7b302-174">Click the **Security** tab.</span></span>  
  
4.  <span data-ttu-id="7b302-175">Si está utilizando IIS 6.0, en el **los nombres de usuario o grupo** casilla de verificación si **cuenta de invitado para Internet** aparece.</span><span class="sxs-lookup"><span data-stu-id="7b302-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="7b302-176">Si no está en la lista:</span><span class="sxs-lookup"><span data-stu-id="7b302-176">If it is not listed:</span></span>  
  
    1.  <span data-ttu-id="7b302-177">Haga clic en **Inicio** y después en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="7b302-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="7b302-178">Si no ve el **cuentas de usuario** icono, haga clic en **cambiar a vista por categorías**.</span><span class="sxs-lookup"><span data-stu-id="7b302-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3.  <span data-ttu-id="7b302-179">Haga clic en el **cuentas de usuario** icono.</span><span class="sxs-lookup"><span data-stu-id="7b302-179">Click the **User Accounts** icon.</span></span>  
  
    4.  <span data-ttu-id="7b302-180">Bajo "o elija un icono del Panel de Control," haga clic en **cuentas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="7b302-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5.  <span data-ttu-id="7b302-181">En el **cuentas de usuario** cuadro de diálogo, haga clic en el **avanzadas** ficha.</span><span class="sxs-lookup"><span data-stu-id="7b302-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6.  <span data-ttu-id="7b302-182">Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="7b302-182">Click **Advanced**.</span></span>  
  
    7.  <span data-ttu-id="7b302-183">En el **usuarios y grupos locales** cuadro de diálogo, haga clic para expandir el **usuarios** carpeta.</span><span class="sxs-lookup"><span data-stu-id="7b302-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8.  <span data-ttu-id="7b302-184">En el panel derecho, haga doble clic en **cuenta de invitado para Internet**.</span><span class="sxs-lookup"><span data-stu-id="7b302-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="7b302-185">En el **propiedades** cuadro de diálogo, copie el nombre se usa como la cuenta de invitado de Internet.</span><span class="sxs-lookup"><span data-stu-id="7b302-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="7b302-186">De forma predeterminada, el nombre comienza con "USR_" seguido por el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="7b302-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="7b302-187">Cerrar la **propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7b302-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="7b302-188">Cerrar la **usuarios y grupos locales** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7b302-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="7b302-189">Cerrar la **cuentas de usuario** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7b302-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="7b302-190">Cerrar la otra **cuentas de usuario** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7b302-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="7b302-191">En el **propiedades de servicemodelsamples** cuadro de diálogo el **seguridad** , haga clic **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7b302-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="7b302-192">Escriba el nombre del equipo seguido por una barra diagonal inversa, a continuación, pegue el nombre de la cuenta de usuario de Internet, por ejemplo, myMachineName\\InternetGuestAccountName %</span><span class="sxs-lookup"><span data-stu-id="7b302-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="7b302-193">Haga clic en **comprobar nombres** para comprobar la adición.</span><span class="sxs-lookup"><span data-stu-id="7b302-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="7b302-194">Si es válido, el nombre está en mayúsculas y subrayado.</span><span class="sxs-lookup"><span data-stu-id="7b302-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5.  <span data-ttu-id="7b302-195">Para IIS 6.0, compruebe también que el servicio de red aparece en el **los nombres de usuario o grupo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="7b302-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="7b302-196">Si el servicio de red no está en la lista:</span><span class="sxs-lookup"><span data-stu-id="7b302-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1.  <span data-ttu-id="7b302-197">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7b302-197">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="7b302-198">En el **Seleccionar usuarios o grupos** cuadro de diálogo, escriba el nombre del equipo seguido por una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="7b302-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3.  <span data-ttu-id="7b302-199">Tipo **servicio** después de la barra diagonal inversa (sin espacio).</span><span class="sxs-lookup"><span data-stu-id="7b302-199">Type **service** after the backslash (no space).</span></span>  
  
    4.  <span data-ttu-id="7b302-200">Haga clic en **comprobar nombres**.</span><span class="sxs-lookup"><span data-stu-id="7b302-200">Click **Check names**.</span></span>  
  
    5.  <span data-ttu-id="7b302-201">Si se encuentran varios nombres, seleccione **NETWORK SERVICE** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b302-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6.  <span data-ttu-id="7b302-202">Haga clic en **Aceptar** para cerrar el **Seleccionar usuarios o grupos** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7b302-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6.  <span data-ttu-id="7b302-203">Si utiliza Windows XP SP2 con IIS 5.1, compruebe que cuenta de invitado para Internet y ASPNET aparecen en la **los nombres de usuario o grupo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="7b302-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="7b302-204">Tenga en cuenta que el usuario ASPNET puede ser un miembro de los integrados **usuarios** grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7b302-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="7b302-205">Si es así, a continuación si el **usuarios** grupo aparece en el cuadro de diálogo, no es necesario agregarlo como un elemento independiente a la lista de usuarios permitidos.</span><span class="sxs-lookup"><span data-stu-id="7b302-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="7b302-206">Para comprobar si ASPNET forma parte de la **usuarios** grupo de seguridad:</span><span class="sxs-lookup"><span data-stu-id="7b302-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1.  <span data-ttu-id="7b302-207">En el **iniciar** menú, haga clic en **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="7b302-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="7b302-208">Haga clic en el **cuentas de usuario** icono.</span><span class="sxs-lookup"><span data-stu-id="7b302-208">Click the **User Accounts** icon.</span></span>  
  
    3.  <span data-ttu-id="7b302-209">En el **grupo** columna, compruebe que el valor de **ASPNET** es "Users".</span><span class="sxs-lookup"><span data-stu-id="7b302-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b302-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b302-210">See also</span></span>

- [<span data-ttu-id="7b302-211">Instrucciones de hospedaje Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="7b302-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
