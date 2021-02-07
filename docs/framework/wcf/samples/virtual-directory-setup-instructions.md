---
description: 'Más información acerca de: instrucciones de configuración del directorio virtual'
title: Instrucciones de configuración del directorio virtual
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 4b1a68fb657a59e9858c6efa7931c5d106231605
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755712"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="75abd-103">Instrucciones de configuración del directorio virtual</span><span class="sxs-lookup"><span data-stu-id="75abd-103">Virtual Directory Setup Instructions</span></span>

<span data-ttu-id="75abd-104">Los ejemplos de Windows Communication Foundation (WCF) están diseñados para compartir un directorio virtual común denominado servicemodelsamples que se asigna a la carpeta%SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="75abd-104">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75abd-105">%SystemDrive% acostumbra a ser C: o D:, según la ubicación de la unidad en que está instalado Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="75abd-105">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="75abd-106">Puede ejecutar los archivos Setupvroot.bat y Cleanupvroot.bat desde el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md) para crear el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="75abd-106">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="75abd-107">Si prefiere crear manualmente el directorio virtual, utilice los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="75abd-107">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="75abd-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="75abd-108">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="75abd-109">Para crear un directorio virtual en IIS 7,0 o 7,5</span><span class="sxs-lookup"><span data-stu-id="75abd-109">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="75abd-110">En el menú **Inicio** , haga clic en **Ejecutar** y, a continuación, escriba **inetmgr** para abrir el complemento MMC de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="75abd-110">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="75abd-111">En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el nodo **sitios** .</span><span class="sxs-lookup"><span data-stu-id="75abd-111">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="75abd-112">Haga clic con el botón secundario en **sitio web predeterminado** y, a continuación, seleccione **Agregar aplicación** para abrir la **ventana Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="75abd-112">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="75abd-113">En la ventana de, escriba `servicemodelsamples` como el alias del directorio virtual que va a crear.</span><span class="sxs-lookup"><span data-stu-id="75abd-113">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="75abd-114">Cree el siguiente directorio: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="75abd-114">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="75abd-115">Especifique la ruta de acceso física a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="75abd-115">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="75abd-116">La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="75abd-116">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="75abd-117">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75abd-117">Click **OK**.</span></span> <span data-ttu-id="75abd-118">Ahora se crea la aplicación web para los ejemplos de WCF.</span><span class="sxs-lookup"><span data-stu-id="75abd-118">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="75abd-119">Esta tarea debe realizarse una sola vez, ya que todos los ejemplos de WCF usan la misma aplicación web servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="75abd-119">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="75abd-120">En esta documentación, el término `virtual directory` es sinónimo de `Web application`.</span><span class="sxs-lookup"><span data-stu-id="75abd-120">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="75abd-121">Además de crear el directorio virtual, también debe establecer sus propiedades para permitir la ejecución de los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="75abd-121">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="75abd-122">Para obtener información más detallada, vea a continuación.</span><span class="sxs-lookup"><span data-stu-id="75abd-122">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="75abd-123">Para crear un directorio virtual en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="75abd-123">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="75abd-124">Abra una ventana del símbolo del sistema y escriba `start inetmgr` para abrir el complemento MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="75abd-124">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="75abd-125">En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el nodo **sitios web** .</span><span class="sxs-lookup"><span data-stu-id="75abd-125">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="75abd-126">Haga clic con el botón secundario en **sitio web predeterminado** y seleccione **nuevo, directorio virtual** para abrir el Asistente para crear un directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="75abd-126">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="75abd-127">En el asistente, escriba `servicemodelsamples` como el alias del directorio virtual que va a crear.</span><span class="sxs-lookup"><span data-stu-id="75abd-127">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="75abd-128">Especifique la ruta de acceso a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="75abd-128">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="75abd-129">La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="75abd-129">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="75abd-130">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75abd-130">Click **Next**.</span></span>  
  
7. <span data-ttu-id="75abd-131">De forma predeterminada, las casillas siguientes están activadas:</span><span class="sxs-lookup"><span data-stu-id="75abd-131">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="75abd-132">**Lectura**</span><span class="sxs-lookup"><span data-stu-id="75abd-132">**Read**</span></span>  
  
    - <span data-ttu-id="75abd-133">**Ejecutar scripts (como ASP)**</span><span class="sxs-lookup"><span data-stu-id="75abd-133">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="75abd-134">Haga clic en **siguiente** y, a continuación, haga clic en **Finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="75abd-134">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="75abd-135">Esta tarea solo se debe realizar una vez porque todos los ejemplos de WCF usan el mismo directorio virtual servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="75abd-135">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="75abd-136">Para establecer propiedades adicionales del directorio virtual en IIS 7,0 o 7,5</span><span class="sxs-lookup"><span data-stu-id="75abd-136">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="75abd-137">Haga clic en el nodo servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="75abd-137">Click the servicemodelsamples node.</span></span> <span data-ttu-id="75abd-138">Se muestran dos vistas en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="75abd-138">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="75abd-139">Seleccione la **vista características** si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="75abd-139">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="75abd-140">Haga doble clic en la entrada para el **examen de directorios**.</span><span class="sxs-lookup"><span data-stu-id="75abd-140">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="75abd-141">En el panel acciones, seleccione la opción **Habilitar** .</span><span class="sxs-lookup"><span data-stu-id="75abd-141">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="75abd-142">Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.</span><span class="sxs-lookup"><span data-stu-id="75abd-142">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="75abd-143">Finalmente, debe establecer las propiedades de seguridad de la carpeta servicemodelsamples para permitir que otros puedan obtener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="75abd-143">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="75abd-144">Para obtener información más detallada, vea a continuación.</span><span class="sxs-lookup"><span data-stu-id="75abd-144">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="75abd-145">Para establecer propiedades de directorio virtual adicionales en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="75abd-145">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="75abd-146">Haga clic con el botón secundario en el nodo servicemodelsamples y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="75abd-146">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="75abd-147">De forma predeterminada, las casillas siguientes están activadas:</span><span class="sxs-lookup"><span data-stu-id="75abd-147">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="75abd-148">**Lectura**</span><span class="sxs-lookup"><span data-stu-id="75abd-148">**Read**</span></span>  
  
    - <span data-ttu-id="75abd-149">**Registrar visitas**</span><span class="sxs-lookup"><span data-stu-id="75abd-149">**Log visits**</span></span>  
  
    - <span data-ttu-id="75abd-150">**Indexar este recurso**</span><span class="sxs-lookup"><span data-stu-id="75abd-150">**Index this resource**</span></span>  
  
3. <span data-ttu-id="75abd-151">Active la casilla **examen de directorios** .</span><span class="sxs-lookup"><span data-stu-id="75abd-151">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="75abd-152">Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.</span><span class="sxs-lookup"><span data-stu-id="75abd-152">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="75abd-153">Para establecer las propiedades de seguridad de la carpeta en IIS 7,0 o 7,5</span><span class="sxs-lookup"><span data-stu-id="75abd-153">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="75abd-154">Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="75abd-154">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="75abd-155">Haga clic con el botón secundario en la carpeta servicemodelsamples y haga clic en **compartir** o **compartir con**.</span><span class="sxs-lookup"><span data-stu-id="75abd-155">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="75abd-156">Haga clic en la flecha abajo a la izquierda del botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="75abd-156">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="75abd-157">Seleccione la entrada **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="75abd-157">Select the **Find** entry.</span></span> <span data-ttu-id="75abd-158">Se abre la ventana **Seleccionar usuarios o grupos** .</span><span class="sxs-lookup"><span data-stu-id="75abd-158">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="75abd-159">Haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="75abd-159">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="75abd-160">Haga clic en **Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="75abd-160">Click **Locations**.</span></span> <span data-ttu-id="75abd-161">La ventana **ubicaciones** ahora está abierta.</span><span class="sxs-lookup"><span data-stu-id="75abd-161">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="75abd-162">Seleccione la entrada para el equipo que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="75abd-162">Select the entry for the computer being used.</span></span> <span data-ttu-id="75abd-163">Es importante seleccionar el equipo local y no una entrada para cualquier dominio o red de la lista.</span><span class="sxs-lookup"><span data-stu-id="75abd-163">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="75abd-164">Después de haber seleccionado el equipo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75abd-164">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="75abd-165">Haz clic en **Buscar ahora**.</span><span class="sxs-lookup"><span data-stu-id="75abd-165">Click **Find Now**.</span></span> <span data-ttu-id="75abd-166">De este modo se rellenan los resultados de la búsqueda con objetos asociados al equipo local.</span><span class="sxs-lookup"><span data-stu-id="75abd-166">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="75abd-167">Busque la entrada **IIS_IUSRS** en la columna **nombre (nombre distintivo relativo)** .</span><span class="sxs-lookup"><span data-stu-id="75abd-167">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="75abd-168">Seleccione la entrada y haga clic en **Aceptar** para cerrar la ventana Resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="75abd-168">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="75abd-169">Haga clic en **Aceptar** para cerrar la ventana **Seleccionar usuarios o grupos** .</span><span class="sxs-lookup"><span data-stu-id="75abd-169">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="75abd-170">Haga clic en **compartir** para conservar los cambios.</span><span class="sxs-lookup"><span data-stu-id="75abd-170">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="75abd-171">Una vez completados los cambios para habilitar el uso compartido, haga clic en **listo** para cerrar la ventana de **uso compartido de archivos** .</span><span class="sxs-lookup"><span data-stu-id="75abd-171">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="75abd-172">Para establecer propiedades de seguridad de la carpeta en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="75abd-172">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="75abd-173">Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="75abd-173">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="75abd-174">Haga clic con el botón secundario en la carpeta **servicemodelsamples** y, a continuación, haga clic en **compartir y seguridad.**</span><span class="sxs-lookup"><span data-stu-id="75abd-174">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="75abd-175">Haga clic en la pestaña **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="75abd-175">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="75abd-176">Si usa IIS 6,0, en el cuadro **nombres de grupos o usuarios** , compruebe si aparece la **cuenta de invitado para Internet** .</span><span class="sxs-lookup"><span data-stu-id="75abd-176">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="75abd-177">Si no es así:</span><span class="sxs-lookup"><span data-stu-id="75abd-177">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="75abd-178">Haga clic en **Inicio** y después en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="75abd-178">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="75abd-179">Si no ve el icono **cuentas de usuario** , haga clic en **cambiar a vista por categorías**.</span><span class="sxs-lookup"><span data-stu-id="75abd-179">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="75abd-180">Haga clic en el icono **cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="75abd-180">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="75abd-181">En "o elija un icono del panel de control", haga clic en **cuentas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="75abd-181">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="75abd-182">En el cuadro de diálogo **cuentas de usuario** , haga clic en la pestaña **Opciones avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="75abd-182">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="75abd-183">Haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="75abd-183">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="75abd-184">En el cuadro de diálogo **usuarios y grupos locales** , haga clic para expandir la carpeta **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="75abd-184">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="75abd-185">En el panel derecho, haga doble clic en **cuenta de invitado para Internet**.</span><span class="sxs-lookup"><span data-stu-id="75abd-185">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="75abd-186">En el cuadro de diálogo **propiedades** , copie el nombre usado como cuenta de invitado para Internet.</span><span class="sxs-lookup"><span data-stu-id="75abd-186">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="75abd-187">De forma predeterminada, el nombre comienza con "USR_" seguido por el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="75abd-187">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="75abd-188">Cierre el cuadro de diálogo **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="75abd-188">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="75abd-189">Cierre el cuadro de diálogo **usuarios y grupos locales** .</span><span class="sxs-lookup"><span data-stu-id="75abd-189">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="75abd-190">Cierre el cuadro de diálogo **cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="75abd-190">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="75abd-191">Cierre el cuadro de diálogo otras **cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="75abd-191">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="75abd-192">En el cuadro de diálogo **propiedades de servicemodelsamples** , en la pestaña **seguridad** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="75abd-192">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="75abd-193">Escriba el nombre del equipo seguido de una barra diagonal inversa y, a continuación, pegue el nombre de la cuenta de usuario de Internet, por ejemplo, myMachineName \\ % InternetGuestAccountName%</span><span class="sxs-lookup"><span data-stu-id="75abd-193">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="75abd-194">Haga clic en **Comprobar nombres** para comprobar la adición.</span><span class="sxs-lookup"><span data-stu-id="75abd-194">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="75abd-195">Si es válido, el nombre está en mayúsculas y subrayado.</span><span class="sxs-lookup"><span data-stu-id="75abd-195">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="75abd-196">Para IIS 6,0, compruebe también que el servicio de red aparece en el cuadro **nombres de grupos o usuarios** .</span><span class="sxs-lookup"><span data-stu-id="75abd-196">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="75abd-197">Si el servicio de red no está en la lista:</span><span class="sxs-lookup"><span data-stu-id="75abd-197">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="75abd-198">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="75abd-198">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="75abd-199">En el cuadro de diálogo **Seleccionar usuarios o grupos** , escriba el nombre del equipo seguido de una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="75abd-199">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="75abd-200">Escriba **Service** después de la barra diagonal inversa (sin espacio).</span><span class="sxs-lookup"><span data-stu-id="75abd-200">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="75abd-201">Haga clic en **Comprobar nombres**.</span><span class="sxs-lookup"><span data-stu-id="75abd-201">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="75abd-202">Si se encuentran varios nombres, seleccione **servicio de red** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75abd-202">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="75abd-203">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Seleccionar usuarios o grupos** .</span><span class="sxs-lookup"><span data-stu-id="75abd-203">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="75abd-204">Si usa Windows XP SP2 con IIS 5,1, compruebe que la cuenta de invitado para Internet y ASPNET aparecen en el cuadro **nombres de grupos o usuarios** .</span><span class="sxs-lookup"><span data-stu-id="75abd-204">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="75abd-205">Tenga en cuenta que el usuario ASPNET puede ser miembro del grupo de seguridad **usuarios** integrados.</span><span class="sxs-lookup"><span data-stu-id="75abd-205">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="75abd-206">Si es así, si el grupo **usuarios** aparece en el cuadro de diálogo, no es necesario agregarlo como un elemento independiente a la lista de usuarios permitidos.</span><span class="sxs-lookup"><span data-stu-id="75abd-206">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="75abd-207">Para comprobar si ASPNET forma parte del grupo de seguridad de **usuarios** :</span><span class="sxs-lookup"><span data-stu-id="75abd-207">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="75abd-208">En el menú **Inicio** , haga clic en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="75abd-208">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="75abd-209">Haga clic en el icono **cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="75abd-209">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="75abd-210">En la columna **Grupo** , compruebe que el valor de **ASPNET** es "usuarios".</span><span class="sxs-lookup"><span data-stu-id="75abd-210">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75abd-211">Vea también</span><span class="sxs-lookup"><span data-stu-id="75abd-211">See also</span></span>

- [<span data-ttu-id="75abd-212">Instrucciones de hospedaje Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="75abd-212">Internet Information Service Hosting Instructions</span></span>](internet-information-service-hosting-instructions.md)
