---
title: Instrucciones de configuración del directorio virtual
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: dba6547888935ccf36ec0924fd3c95e8fbda5688
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243656"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="f19e1-102">Instrucciones de configuración del directorio virtual</span><span class="sxs-lookup"><span data-stu-id="f19e1-102">Virtual Directory Setup Instructions</span></span>

<span data-ttu-id="f19e1-103">Los ejemplos de Windows Communication Foundation (WCF) están diseñados para compartir un directorio virtual común denominado servicemodelsamples que se asigna a la carpeta%SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="f19e1-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f19e1-104">%SystemDrive% acostumbra a ser C: o D:, según la ubicación de la unidad en que está instalado Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="f19e1-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="f19e1-105">Puede ejecutar los archivos Setupvroot.bat y Cleanupvroot.bat desde el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md) para crear el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="f19e1-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="f19e1-106">Si prefiere crear manualmente el directorio virtual, utilice los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f19e1-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f19e1-107">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="f19e1-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="f19e1-108">Para crear un directorio virtual en IIS 7,0 o 7,5</span><span class="sxs-lookup"><span data-stu-id="f19e1-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="f19e1-109">En el menú **Inicio** , haga clic en **Ejecutar** y, a continuación, escriba **inetmgr** para abrir el complemento MMC de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="f19e1-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="f19e1-110">En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el nodo **sitios** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="f19e1-111">Haga clic con el botón secundario en **sitio web predeterminado** y, a continuación, seleccione **Agregar aplicación** para abrir la **ventana Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="f19e1-112">En la ventana de, escriba `servicemodelsamples` como el alias del directorio virtual que va a crear.</span><span class="sxs-lookup"><span data-stu-id="f19e1-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="f19e1-113">Cree el siguiente directorio: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="f19e1-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="f19e1-114">Especifique la ruta de acceso física a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="f19e1-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="f19e1-115">La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="f19e1-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="f19e1-116">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-116">Click **OK**.</span></span> <span data-ttu-id="f19e1-117">Ahora se crea la aplicación web para los ejemplos de WCF.</span><span class="sxs-lookup"><span data-stu-id="f19e1-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f19e1-118">Esta tarea debe realizarse una sola vez, ya que todos los ejemplos de WCF usan la misma aplicación web servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="f19e1-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f19e1-119">En esta documentación, el término `virtual directory` es sinónimo de `Web application`.</span><span class="sxs-lookup"><span data-stu-id="f19e1-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="f19e1-120">Además de crear el directorio virtual, también debe establecer sus propiedades para permitir la ejecución de los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="f19e1-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="f19e1-121">Consulte a continuación para más información.</span><span class="sxs-lookup"><span data-stu-id="f19e1-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="f19e1-122">Para crear un directorio virtual en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="f19e1-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="f19e1-123">Abra una ventana del símbolo del sistema y escriba `start inetmgr` para abrir el complemento MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="f19e1-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="f19e1-124">En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el nodo **sitios web** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="f19e1-125">Haga clic con el botón secundario en **sitio web predeterminado** y seleccione **nuevo, directorio virtual** para abrir el Asistente para crear un directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="f19e1-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="f19e1-126">En el asistente, escriba `servicemodelsamples` como el alias del directorio virtual que va a crear.</span><span class="sxs-lookup"><span data-stu-id="f19e1-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="f19e1-127">Especifique la ruta de acceso a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="f19e1-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="f19e1-128">La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.</span><span class="sxs-lookup"><span data-stu-id="f19e1-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="f19e1-129">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="f19e1-130">De forma predeterminada, las casillas siguientes están activadas:</span><span class="sxs-lookup"><span data-stu-id="f19e1-130">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="f19e1-131">**Lectura**</span><span class="sxs-lookup"><span data-stu-id="f19e1-131">**Read**</span></span>  
  
    - <span data-ttu-id="f19e1-132">**Ejecutar scripts (como ASP)**</span><span class="sxs-lookup"><span data-stu-id="f19e1-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="f19e1-133">Haga clic en **siguiente** y, a continuación, haga clic en **Finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="f19e1-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f19e1-134">Esta tarea solo se debe realizar una vez porque todos los ejemplos de WCF usan el mismo directorio virtual servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="f19e1-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="f19e1-135">Para establecer propiedades adicionales del directorio virtual en IIS 7,0 o 7,5</span><span class="sxs-lookup"><span data-stu-id="f19e1-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="f19e1-136">Haga clic en el nodo servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="f19e1-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="f19e1-137">Se muestran dos vistas en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="f19e1-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="f19e1-138">Seleccione la **vista características** si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f19e1-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="f19e1-139">Haga doble clic en la entrada para el **examen de directorios**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="f19e1-140">En el panel acciones, seleccione la opción **Habilitar** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="f19e1-141">Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.</span><span class="sxs-lookup"><span data-stu-id="f19e1-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="f19e1-142">Finalmente, debe establecer las propiedades de seguridad de la carpeta servicemodelsamples para permitir que otros puedan obtener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="f19e1-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="f19e1-143">Consulte a continuación para más información.</span><span class="sxs-lookup"><span data-stu-id="f19e1-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="f19e1-144">Para establecer propiedades de directorio virtual adicionales en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="f19e1-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="f19e1-145">Haga clic con el botón secundario en el nodo servicemodelsamples y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="f19e1-146">De forma predeterminada, las casillas siguientes están activadas:</span><span class="sxs-lookup"><span data-stu-id="f19e1-146">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="f19e1-147">**Lectura**</span><span class="sxs-lookup"><span data-stu-id="f19e1-147">**Read**</span></span>  
  
    - <span data-ttu-id="f19e1-148">**Registrar visitas**</span><span class="sxs-lookup"><span data-stu-id="f19e1-148">**Log visits**</span></span>  
  
    - <span data-ttu-id="f19e1-149">**Indexar este recurso**</span><span class="sxs-lookup"><span data-stu-id="f19e1-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="f19e1-150">Active la casilla **examen de directorios** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="f19e1-151">Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.</span><span class="sxs-lookup"><span data-stu-id="f19e1-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="f19e1-152">Para establecer las propiedades de seguridad de la carpeta en IIS 7,0 o 7,5</span><span class="sxs-lookup"><span data-stu-id="f19e1-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="f19e1-153">Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="f19e1-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="f19e1-154">Haga clic con el botón secundario en la carpeta servicemodelsamples y haga clic en **compartir** o **compartir con**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="f19e1-155">Haga clic en la flecha abajo a la izquierda del botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="f19e1-156">Seleccione la entrada **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-156">Select the **Find** entry.</span></span> <span data-ttu-id="f19e1-157">Se abre la ventana **Seleccionar usuarios o grupos** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="f19e1-158">Haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="f19e1-159">Haga clic en **Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-159">Click **Locations**.</span></span> <span data-ttu-id="f19e1-160">La ventana **ubicaciones** ahora está abierta.</span><span class="sxs-lookup"><span data-stu-id="f19e1-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="f19e1-161">Seleccione la entrada para el equipo que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="f19e1-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="f19e1-162">Es importante seleccionar el equipo local y no una entrada para cualquier dominio o red de la lista.</span><span class="sxs-lookup"><span data-stu-id="f19e1-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="f19e1-163">Después de haber seleccionado el equipo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="f19e1-164">Haz clic en **Buscar ahora**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-164">Click **Find Now**.</span></span> <span data-ttu-id="f19e1-165">De este modo se rellenan los resultados de la búsqueda con objetos asociados al equipo local.</span><span class="sxs-lookup"><span data-stu-id="f19e1-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="f19e1-166">Busque la entrada **IIS_IUSRS** en la columna **nombre (nombre distintivo relativo)** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="f19e1-167">Seleccione la entrada y haga clic en **Aceptar** para cerrar la ventana Resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f19e1-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="f19e1-168">Haga clic en **Aceptar** para cerrar la ventana **Seleccionar usuarios o grupos** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="f19e1-169">Haga clic en **compartir** para conservar los cambios.</span><span class="sxs-lookup"><span data-stu-id="f19e1-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="f19e1-170">Una vez completados los cambios para habilitar el uso compartido, haga clic en **listo** para cerrar la ventana de **uso compartido de archivos** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="f19e1-171">Para establecer propiedades de seguridad de la carpeta en IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="f19e1-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="f19e1-172">Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="f19e1-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="f19e1-173">Haga clic con el botón secundario en la carpeta **servicemodelsamples** y, a continuación, haga clic en **compartir y seguridad.**</span><span class="sxs-lookup"><span data-stu-id="f19e1-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="f19e1-174">Haga clic en la pestaña **Security** (Seguridad).</span><span class="sxs-lookup"><span data-stu-id="f19e1-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="f19e1-175">Si usa IIS 6,0, en el cuadro **nombres de grupos o usuarios** , compruebe si aparece la **cuenta de invitado para Internet** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="f19e1-176">Si no es así:</span><span class="sxs-lookup"><span data-stu-id="f19e1-176">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="f19e1-177">Haga clic en **Inicio** y después en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="f19e1-178">Si no ve el icono **cuentas de usuario** , haga clic en **cambiar a vista por categorías**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="f19e1-179">Haga clic en el icono **cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-179">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="f19e1-180">En "o elija un icono del panel de control", haga clic en **cuentas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="f19e1-181">En el cuadro de diálogo **cuentas de usuario** , haga clic en la pestaña **Opciones avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="f19e1-182">Haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-182">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="f19e1-183">En el cuadro de diálogo **usuarios y grupos locales** , haga clic para expandir la carpeta **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="f19e1-184">En el panel derecho, haga doble clic en **cuenta de invitado para Internet**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="f19e1-185">En el cuadro de diálogo **propiedades** , copie el nombre usado como cuenta de invitado para Internet.</span><span class="sxs-lookup"><span data-stu-id="f19e1-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="f19e1-186">De forma predeterminada, el nombre comienza con "USR_" seguido por el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="f19e1-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="f19e1-187">Cierre el cuadro de diálogo **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="f19e1-188">Cierre el cuadro de diálogo **usuarios y grupos locales** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="f19e1-189">Cierre el cuadro de diálogo **cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="f19e1-190">Cierre el cuadro de diálogo otras **cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="f19e1-191">En el cuadro de diálogo **propiedades de servicemodelsamples** , en la pestaña **seguridad** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="f19e1-192">Escriba el nombre del equipo seguido de una barra diagonal inversa y, a continuación, pegue el nombre de la cuenta de usuario de Internet, por ejemplo, myMachineName \\ % InternetGuestAccountName%</span><span class="sxs-lookup"><span data-stu-id="f19e1-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="f19e1-193">Haga clic en **Comprobar nombres** para comprobar la adición.</span><span class="sxs-lookup"><span data-stu-id="f19e1-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="f19e1-194">Si es válido, el nombre está en mayúsculas y subrayado.</span><span class="sxs-lookup"><span data-stu-id="f19e1-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="f19e1-195">Para IIS 6,0, compruebe también que el servicio de red aparece en el cuadro **nombres de grupos o usuarios** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="f19e1-196">Si el servicio de red no está en la lista:</span><span class="sxs-lookup"><span data-stu-id="f19e1-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="f19e1-197">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-197">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="f19e1-198">En el cuadro de diálogo **Seleccionar usuarios o grupos** , escriba el nombre del equipo seguido de una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="f19e1-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="f19e1-199">Escriba **Service** después de la barra diagonal inversa (sin espacio).</span><span class="sxs-lookup"><span data-stu-id="f19e1-199">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="f19e1-200">Haga clic en **Comprobar nombres**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-200">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="f19e1-201">Si se encuentran varios nombres, seleccione **servicio de red** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="f19e1-202">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Seleccionar usuarios o grupos** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="f19e1-203">Si usa Windows XP SP2 con IIS 5,1, compruebe que la cuenta de invitado para Internet y ASPNET aparecen en el cuadro **nombres de grupos o usuarios** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="f19e1-204">Tenga en cuenta que el usuario ASPNET puede ser miembro del grupo de seguridad **usuarios** integrados.</span><span class="sxs-lookup"><span data-stu-id="f19e1-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="f19e1-205">Si es así, si el grupo **usuarios** aparece en el cuadro de diálogo, no es necesario agregarlo como un elemento independiente a la lista de usuarios permitidos.</span><span class="sxs-lookup"><span data-stu-id="f19e1-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="f19e1-206">Para comprobar si ASPNET forma parte del grupo de seguridad de **usuarios** :</span><span class="sxs-lookup"><span data-stu-id="f19e1-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="f19e1-207">En el menú **Inicio** , haga clic en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="f19e1-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="f19e1-208">Haga clic en el icono **cuentas de usuario** .</span><span class="sxs-lookup"><span data-stu-id="f19e1-208">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="f19e1-209">En la columna **Grupo** , compruebe que el valor de **ASPNET** es "usuarios".</span><span class="sxs-lookup"><span data-stu-id="f19e1-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f19e1-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="f19e1-210">See also</span></span>

- [<span data-ttu-id="f19e1-211">Instrucciones de hospedaje Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="f19e1-211">Internet Information Service Hosting Instructions</span></span>](internet-information-service-hosting-instructions.md)
