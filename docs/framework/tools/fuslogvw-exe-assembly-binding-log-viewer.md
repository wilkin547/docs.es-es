---
title: Fuslogvw.exe (Visor de registro de enlaces de ensamblados)
description: Use Fuslogvw.exe, el visor de registro de enlaces de ensamblados. Este visor muestra los detalles de los enlaces de ensamblados, lo que ayuda a diagnosticar por qué .NET no encuentra un ensamblado en tiempo de ejecución.
ms.date: 03/30/2017
helpviewer_keywords:
- failed assembly binds
- Fuslogvw.exe
- displaying failed assembly bind details
- assemblies [.NET Framework], failed assembly binds
- locating assemblies
- Assembly Binding Log Viewer
ms.assetid: e32fa443-0778-4cc3-bf36-5c8ea297d296
ms.openlocfilehash: 949f9cf98d5eb4e100be9837be120038f085cc40
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167121"
---
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a><span data-ttu-id="187fb-104">Fuslogvw.exe (Visor de registro de enlaces de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="187fb-104">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>

<span data-ttu-id="187fb-105">El Visor de registro de enlaces de ensamblados es una herramienta que muestra los detalles de los enlaces de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="187fb-105">The Assembly Binding Log Viewer displays details for assembly binds.</span></span> <span data-ttu-id="187fb-106">Esta información ayuda a diagnosticar la causa por la que .NET Framework no puede encontrar un ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="187fb-106">This information helps you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span> <span data-ttu-id="187fb-107">Normalmente, estos errores se deben a que el ensamblado se ha implementado en una ubicación incorrecta, a que una imagen nativa ha dejado de ser válida o a que los números de versiones o referencias culturales no coinciden.</span><span class="sxs-lookup"><span data-stu-id="187fb-107">These failures are usually the result of an assembly deployed to the wrong location, a native image that is no longer valid, or a mismatch in version numbers or cultures.</span></span> <span data-ttu-id="187fb-108">Normalmente, el error de Common Language Runtime al localizar un ensamblado se muestra como <xref:System.TypeLoadException> en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="187fb-108">The common language runtime's failure to locate an assembly typically shows up as a <xref:System.TypeLoadException> in your application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="187fb-109">Debe ejecutar fuslogvw.exe con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="187fb-109">You must run fuslogvw.exe with administrator privileges.</span></span>

<span data-ttu-id="187fb-110">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="187fb-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="187fb-111">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7) con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="187fb-111">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7) with administrator credentials.</span></span> <span data-ttu-id="187fb-112">Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="187fb-112">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="187fb-113">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="187fb-113">At the command prompt, type the following:</span></span>

```console
fuslogvw
```

<span data-ttu-id="187fb-114">El visor muestra una entrada para cada enlace de ensamblado con errores.</span><span class="sxs-lookup"><span data-stu-id="187fb-114">The viewer displays an entry for each failed assembly bind.</span></span> <span data-ttu-id="187fb-115">Para cada error, el visor describe la aplicación en la que se inició el enlace; el ensamblado para el que se realiza el enlace, incluidos el nombre, la versión, la referencia cultural y la clave pública; y la fecha y la hora del error.</span><span class="sxs-lookup"><span data-stu-id="187fb-115">For each failure, the viewer describes the application that initiated the bind; the assembly the bind is for, including name, version, culture and public key; and the date and time of the failure.</span></span>

### <a name="to-change-the-log-location-view"></a><span data-ttu-id="187fb-116">Para cambiar la vista de la ubicación del registro</span><span class="sxs-lookup"><span data-stu-id="187fb-116">To change the log location view</span></span>

1. <span data-ttu-id="187fb-117">Seleccione el botón de opción **Predeterminado** para ver los errores de enlaces de todos los tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="187fb-117">Select the **Default** option button to view bind failures for all application types.</span></span> <span data-ttu-id="187fb-118">De forma predeterminada, las entradas del registro se almacenan por directorios de usuario en la memoria caché wininet del disco.</span><span class="sxs-lookup"><span data-stu-id="187fb-118">By default, log entries are stored in per-user directories on disk in the wininet cache.</span></span>

2. <span data-ttu-id="187fb-119">Seleccione el botón de opción **Personalizar** para ver los errores de enlaces en un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="187fb-119">Select the **Custom** option button to view bind failures in a custom directory that you specify.</span></span> <span data-ttu-id="187fb-120">Debe especificar la ubicación personalizada en la que quiere que el tiempo de ejecución almacene los registros; para ello, establezca la ubicación del registro predeterminada en un nombre de directorio válido en el cuadro de diálogo **Configuración de registro**.</span><span class="sxs-lookup"><span data-stu-id="187fb-120">You must specify the custom location where you want the runtime to store the logs by setting the custom log location in the **Log Settings** dialog to a valid directory name.</span></span> <span data-ttu-id="187fb-121">Este directorio debe estar limpio y solo debe contener los archivos que genere el runtime.</span><span class="sxs-lookup"><span data-stu-id="187fb-121">This directory should be clean, and only contain files that the runtime generates.</span></span> <span data-ttu-id="187fb-122">Si contiene un ejecutable que genera un error que se deba registrar, este no se registrará porque la herramienta intenta crear un directorio con el mismo nombre que el ejecutable.</span><span class="sxs-lookup"><span data-stu-id="187fb-122">If it contains an executable that generates a failure to be logged, the failure will not be logged because the tool tries to create a directory with the same name as the executable.</span></span> <span data-ttu-id="187fb-123">Además, los intentos de ejecutar archivos ejecutables desde la ubicación del registro generarán un error.</span><span class="sxs-lookup"><span data-stu-id="187fb-123">In addition, an attempt to run an executable from the log location will fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="187fb-124">Es preferible usar la ubicación de enlace predeterminada en lugar de la ubicación de enlace personalizada.</span><span class="sxs-lookup"><span data-stu-id="187fb-124">The default bind location is preferable to the custom bind location.</span></span> <span data-ttu-id="187fb-125">El runtime almacena la ubicación de enlace predeterminada en la memoria caché wininet que, de esta forma, se limpia automáticamente. Si especifica una ubicación de enlace personalizada, es responsabilidad suya limpiarla.</span><span class="sxs-lookup"><span data-stu-id="187fb-125">The runtime stores the default bind location in the wininet cache, and therefore automatically cleans it out. If you specify a custom bind location, you are responsible for cleaning it out.</span></span>

### <a name="to-view-details-about-a-specific-failure"></a><span data-ttu-id="187fb-126">Para ver los detalles de un error específico</span><span class="sxs-lookup"><span data-stu-id="187fb-126">To view details about a specific failure</span></span>

1. <span data-ttu-id="187fb-127">Seleccione en el visor el nombre de la aplicación de la entrada que desea ver.</span><span class="sxs-lookup"><span data-stu-id="187fb-127">Select the application name of the desired entry in the viewer.</span></span>

2. <span data-ttu-id="187fb-128">Haga clic en el botón **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="187fb-128">Click the **View Log** button.</span></span> <span data-ttu-id="187fb-129">Otra posibilidad es hacer doble clic en la entrada seleccionada.</span><span class="sxs-lookup"><span data-stu-id="187fb-129">Alternately, you can double-click the selected entry.</span></span>

    <span data-ttu-id="187fb-130">La herramienta muestra los siguientes detalles sobre el error de enlace seleccionado:</span><span class="sxs-lookup"><span data-stu-id="187fb-130">The tool displays the following details about the selected bind failure:</span></span>

    - <span data-ttu-id="187fb-131">El motivo específico del error del enlace, como "Archivo no encontrado" o "No coinciden las versiones".</span><span class="sxs-lookup"><span data-stu-id="187fb-131">The specific reason the bind failed, such as "file not found" or "version mismatch".</span></span>

    - <span data-ttu-id="187fb-132">Información sobre la aplicación que inició el enlace, incluidos el nombre y el directorio raíz de la aplicación (AppBase) y una descripción de la ruta de acceso de búsqueda privada, si existe.</span><span class="sxs-lookup"><span data-stu-id="187fb-132">Information about the application that initiated the bind, including its name, the application's root directory (AppBase), and a description of the private search path, if there is one.</span></span>

    - <span data-ttu-id="187fb-133">La identidad del ensamblado que busca la herramienta.</span><span class="sxs-lookup"><span data-stu-id="187fb-133">The identity of the assembly the tool is looking for.</span></span>

    - <span data-ttu-id="187fb-134">Una descripción de las directivas de versión (aplicación, edición o administrador) que se han aplicado.</span><span class="sxs-lookup"><span data-stu-id="187fb-134">A description of any Application, Publisher, or Administrator version policies that have been applied.</span></span>

    - <span data-ttu-id="187fb-135">Si se ha encontrado el ensamblado en la [caché global de ensamblados](../app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="187fb-135">Whether the assembly was found in the [global assembly cache](../app-domains/gac.md).</span></span>

    - <span data-ttu-id="187fb-136">Una lista de todas las direcciones URL de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="187fb-136">A list of all probing URLs.</span></span>

<span data-ttu-id="187fb-137">En el siguiente ejemplo de entrada del registro se muestra información detallada sobre un enlace de ensamblado con errores.</span><span class="sxs-lookup"><span data-stu-id="187fb-137">The following sample log entry shows detailed information about a failed assembly bind.</span></span>

```output
*** Assembly Binder Log Entry  (3/5/2007 @ 12:54:20 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  C:\WINNT\Microsoft.NET\Framework\v2.0.50727\fusion.dll
Running under executable  C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\graphicfailtest.exe
--- A detailed error log follows.

=== Pre-bind state information ===
LOG: DisplayName = graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
 (Fully-specified)
LOG: Appbase = C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\
LOG: Initial PrivatePath = NULL
LOG: Dynamic Base = NULL
LOG: Cache Base = NULL
LOG: AppName = NULL
Calling assembly : graphicfailtest, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
===

LOG: Processing DEVPATH.
LOG: DEVPATH is not set. Falling through to regular bind.
LOG: Policy not being applied to reference at this time (private, custom, partial, or location-based assembly bind).
LOG: Post-policy reference: graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.EXE.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.EXE.
LOG: All probing URLs attempted and failed.
```

### <a name="to-delete-a-single-entry-from-the-log"></a><span data-ttu-id="187fb-138">Para eliminar una entrada del registro</span><span class="sxs-lookup"><span data-stu-id="187fb-138">To delete a single entry from the log</span></span>

1. <span data-ttu-id="187fb-139">Seleccione la entrada en el visor.</span><span class="sxs-lookup"><span data-stu-id="187fb-139">Select an entry in the viewer.</span></span>

2. <span data-ttu-id="187fb-140">Haga clic en el botón **Eliminar entrada**.</span><span class="sxs-lookup"><span data-stu-id="187fb-140">Click the **Delete Entry** button.</span></span>

### <a name="to-delete-all-entries-from-the-log"></a><span data-ttu-id="187fb-141">Para eliminar todas las entradas del registro</span><span class="sxs-lookup"><span data-stu-id="187fb-141">To delete all entries from the log</span></span>

- <span data-ttu-id="187fb-142">Haga clic en el botón **Eliminar todo**.</span><span class="sxs-lookup"><span data-stu-id="187fb-142">Click the **Delete All** button.</span></span>

### <a name="to-refresh-the-user-interface"></a><span data-ttu-id="187fb-143">Para actualizar la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="187fb-143">To refresh the user interface</span></span>

- <span data-ttu-id="187fb-144">Haga clic en el botón **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="187fb-144">Click the **Refresh** button.</span></span> <span data-ttu-id="187fb-145">Mientras se ejecuta, el visor no detecta automáticamente las entradas nuevas del registro.</span><span class="sxs-lookup"><span data-stu-id="187fb-145">The viewer does not automatically detect new log entries while it is running.</span></span> <span data-ttu-id="187fb-146">Debe usar el botón **Actualizar** para mostrarlas.</span><span class="sxs-lookup"><span data-stu-id="187fb-146">You must use the **Refresh** button to display them.</span></span>

### <a name="to-change-the-log-settings"></a><span data-ttu-id="187fb-147">Para cambiar la configuración de registro</span><span class="sxs-lookup"><span data-stu-id="187fb-147">To change the log settings</span></span>

- <span data-ttu-id="187fb-148">Haga clic en el botón **Configuración** para abrir el cuadro de diálogo **Configuración de registro**.</span><span class="sxs-lookup"><span data-stu-id="187fb-148">Click the **Settings** button to open the **Log Settings** dialog.</span></span>

### <a name="to-view-the-about-dialog"></a><span data-ttu-id="187fb-149">Para ver el cuadro de diálogo Acerca de</span><span class="sxs-lookup"><span data-stu-id="187fb-149">To view the About dialog</span></span>

- <span data-ttu-id="187fb-150">Haga clic en el botón **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="187fb-150">Click the **About** button.</span></span>

## <a name="binding-logs-for-native-images"></a><span data-ttu-id="187fb-151">Registros de enlaces de las imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="187fb-151">Binding Logs for Native Images</span></span>

<span data-ttu-id="187fb-152">De forma predeterminada, Fuslogvw.exe registra las solicitudes de enlace de ensamblado normales.</span><span class="sxs-lookup"><span data-stu-id="187fb-152">By default, Fuslogvw.exe logs normal assembly bind requests.</span></span> <span data-ttu-id="187fb-153">También tiene la opción de registrar los enlaces de ensamblado de las imágenes nativas creadas mediante [Ngen.exe (Generador de imágenes nativas)](ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="187fb-153">Alternatively, you can log assembly binds for native images that were created using the [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md).</span></span>

#### <a name="to-log-assembly-binds-for-native-images"></a><span data-ttu-id="187fb-154">Para registrar los enlaces de ensamblado de las imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="187fb-154">To log assembly binds for native images</span></span>

- <span data-ttu-id="187fb-155">En el grupo **Categorías de registro**, seleccione el botón de opción **Imágenes nativas**.</span><span class="sxs-lookup"><span data-stu-id="187fb-155">In the **Log Categories** group, select the **Native Images** option button.</span></span>

<span data-ttu-id="187fb-156">El registro siguiente muestra un error producido por una dependencia que no existía cuando se creó la imagen nativa para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="187fb-156">The following log shows a failure caused by a dependency that did not exist when the native image was created for the application.</span></span> <span data-ttu-id="187fb-157">Si las dependencias en tiempo de ejecución difieren de las dependencias en el momento de la ejecución de Ngen.exe, no se permitirá el enlace a una imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="187fb-157">If the dependencies at run time differ from the dependencies when Ngen.exe is run, binding to a native image is not allowed.</span></span>

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:22:07 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\App.exe
--- A detailed error log follows.

LOG: Start binding of native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\App.exe.
LOG: Start validating native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency b, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
WRN: Dependency assembly was not found at ngen time, but is found at binding time. Disallow using this native image.
WRN: No matching native image found.
LOG: Bind to native image assembly did not succeed. Use IL image.
```

<span data-ttu-id="187fb-158">El registro siguiente muestra un error de enlace a una imagen nativa producido porque la configuración de seguridad del equipo cuando se ejecutó la aplicación era distinta de la configuración de seguridad en el momento en que se creó la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="187fb-158">The following log shows a native image binding failure that occurred because the security settings on the computer when the application was run were different from the security settings at the time the native image was created.</span></span>

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:29:09 PM) ***

The operation failed.
Bind result: hr = 0x80004005. Unspecified error

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\Application101622.exe
--- A detailed error log follows.

LOG: Start binding of native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\Application101622.exe.
LOG: Start validating native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency Dependency101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Dependency evaluation succeeded.
LOG: Validation of dependencies succeeded.
LOG: Start loading all the dependencies into load context.
LOG: Loading of dependencies succeeded.
LOG: Bind to native image succeeded.
Native image has correct version information.
Attempting to use native image E:\Windows\assembly\NativeImages_v2.0.50727_64\Application101622\1ac7fadabec4f72575d807501e9fdc72\Application101622.ni.exe.
Rejecting native image because it failed the security check. The assembly's permissions must have changed since the time it was ngenned, or it is running with a different security context.
Discarding native image.
```

## <a name="the-log-settings-dialog"></a><span data-ttu-id="187fb-159">El cuadro de diálogo Configuración de registro</span><span class="sxs-lookup"><span data-stu-id="187fb-159">The Log Settings Dialog</span></span>

<span data-ttu-id="187fb-160">Puede usar el cuadro de diálogo **Configuración de registro** para realizar las acciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="187fb-160">You can use the **Log Settings** dialog to perform the following actions.</span></span>

#### <a name="to-disable-logging"></a><span data-ttu-id="187fb-161">Para deshabilitar el registro</span><span class="sxs-lookup"><span data-stu-id="187fb-161">To disable logging</span></span>

- <span data-ttu-id="187fb-162">Seleccione el botón de opción **Registro deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="187fb-162">Select the **Log disabled** option button.</span></span>  <span data-ttu-id="187fb-163">Tenga en cuenta que esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="187fb-163">Note that this option is selected by default.</span></span>

#### <a name="to-log-assembly-binds-in-exceptions"></a><span data-ttu-id="187fb-164">Para registrar enlaces de ensamblado en excepciones</span><span class="sxs-lookup"><span data-stu-id="187fb-164">To log assembly binds in exceptions</span></span>

- <span data-ttu-id="187fb-165">Seleccione el botón de opción **Registrar texto de excepciones**.</span><span class="sxs-lookup"><span data-stu-id="187fb-165">Select the **Log in exception text** option button.</span></span> <span data-ttu-id="187fb-166">En el texto de excepciones solo se registra la información de registro de Fusion menos detallada.</span><span class="sxs-lookup"><span data-stu-id="187fb-166">Only the least detailed fusion log information is logged in exception text.</span></span> <span data-ttu-id="187fb-167">Para ver toda la información, use cualquier otra opción.</span><span class="sxs-lookup"><span data-stu-id="187fb-167">To view full information, use one of the other settings.</span></span>

  <span data-ttu-id="187fb-168">Vea la nota Importante referente a los ensamblados que se cargan como dominios neutros.</span><span class="sxs-lookup"><span data-stu-id="187fb-168">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-assembly-bind-failures"></a><span data-ttu-id="187fb-169">Para registrar los errores de enlace de ensamblado</span><span class="sxs-lookup"><span data-stu-id="187fb-169">To log assembly bind failures</span></span>

- <span data-ttu-id="187fb-170">Seleccione el botón de opción **Registrar errores de enlace en el disco**.</span><span class="sxs-lookup"><span data-stu-id="187fb-170">Select the **Log bind failures to disk** option button.</span></span>

  <span data-ttu-id="187fb-171">Vea la nota Importante referente a los ensamblados que se cargan como dominios neutros.</span><span class="sxs-lookup"><span data-stu-id="187fb-171">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

#### <a name="to-log-all-assembly-binds"></a><span data-ttu-id="187fb-172">Para registrar todos los enlaces de ensamblado</span><span class="sxs-lookup"><span data-stu-id="187fb-172">To log all assembly binds</span></span>

- <span data-ttu-id="187fb-173">Seleccione el botón de opción **Registrar todos los enlaces en el disco**.</span><span class="sxs-lookup"><span data-stu-id="187fb-173">Select the **Log all binds to disk** option button.</span></span>

  <span data-ttu-id="187fb-174">Vea la nota Importante referente a los ensamblados que se cargan como dominios neutros.</span><span class="sxs-lookup"><span data-stu-id="187fb-174">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="187fb-175">Cuando se carga un ensamblado como dominio neutro, por ejemplo, mediante el establecimiento de la propiedad <xref:System.AppDomainSetup.LoaderOptimization%2A> en <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> o <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, en algunos casos la activación del registro puede originar pérdidas de memoria.</span><span class="sxs-lookup"><span data-stu-id="187fb-175">When an assembly is loaded as domain neutral, for example by setting the <xref:System.AppDomainSetup.LoaderOptimization%2A> property to <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> or <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, turning on logging might leak memory in some cases.</span></span> <span data-ttu-id="187fb-176">Esto puede suceder si se realiza una entrada de registro al cargar un módulo con dominio neutro en un dominio de aplicación y, posteriormente, se descarga el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="187fb-176">This can happen if a log entry is made when a domain-neutral module is loaded into an application domain, and later the application domain is unloaded.</span></span> <span data-ttu-id="187fb-177">Puede ocurrir que la entrada de registro no se libere hasta que finalice el proceso.</span><span class="sxs-lookup"><span data-stu-id="187fb-177">The log entry might not be released until the process ends.</span></span> <span data-ttu-id="187fb-178">Algunos depuradores activan automáticamente el registro.</span><span class="sxs-lookup"><span data-stu-id="187fb-178">Some debuggers automatically turn on logging.</span></span>

#### <a name="to-enable-a-custom-log-path"></a><span data-ttu-id="187fb-179">Para habilitar una ruta de acceso de registro personalizada</span><span class="sxs-lookup"><span data-stu-id="187fb-179">To enable a custom log path</span></span>

1. <span data-ttu-id="187fb-180">Seleccione el botón de opción **Habilitar ruta de acceso de registro personalizada**.</span><span class="sxs-lookup"><span data-stu-id="187fb-180">Select the **Enable custom log path** option button.</span></span>

2. <span data-ttu-id="187fb-181">Escriba la ruta de acceso en el cuadro de texto **Ruta de acceso de registro personalizada**.</span><span class="sxs-lookup"><span data-stu-id="187fb-181">Enter the path into the **Custom log path** text box.</span></span>

> [!NOTE]
> <span data-ttu-id="187fb-182">El [Visor de registro de enlaces de ensamblados (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) usa la memoria caché de Internet Explorer (IE) para almacenar el registro de enlaces.</span><span class="sxs-lookup"><span data-stu-id="187fb-182">The [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) uses the Internet Explorer (IE) cache to store its binding log.</span></span> <span data-ttu-id="187fb-183">Debido a daños ocasionales en la memoria caché de IE, a veces el [Visor de registro de enlaces de ensamblados (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) deja de mostrar los nuevos registros de enlaces en la ventana de visualización.</span><span class="sxs-lookup"><span data-stu-id="187fb-183">Due to occasional corruption in the IE cache, the [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) can sometimes stop showing new binding logs in the viewing window.</span></span> <span data-ttu-id="187fb-184">Como consecuencia de estos daños, la infraestructura de enlaces (Fusion) de .NET no puede escribir en el registro de enlaces ni leerlo.</span><span class="sxs-lookup"><span data-stu-id="187fb-184">As a result of this corruption, the .NET binding infrastructure (fusion) cannot write to or read from the binding log.</span></span> <span data-ttu-id="187fb-185">(Este problema no aparece si se usa una ruta de acceso de registro personalizada).  Para corregir los daños y permitir que Fusion vuelva a mostrar los registros de enlaces, borre la memoria caché de IE; para ello, elimine los archivos temporales de Internet en el cuadro de diálogo Opciones de Internet de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="187fb-185">(This issue is not encountered if you use a custom log path.)  To fix the corruption and allow fusion to show binding logs again, clear the IE cache by deleting temporary internet files from within the IE Internet Options dialog.</span></span>
>
> <span data-ttu-id="187fb-186">Si la aplicación no administrada hospeda Common Language Runtime mediante la implementación de las interfaces `IHostAssemblyManager` e `IHostAssemblyStore`, las entradas de registro no pueden almacenarse en la memoria caché de wininet.</span><span class="sxs-lookup"><span data-stu-id="187fb-186">If your unmanaged application hosts the common language runtime by implementing the `IHostAssemblyManager` and `IHostAssemblyStore` interfaces, log entries can't be stored in the wininet cache.</span></span>  <span data-ttu-id="187fb-187">Para ver las entradas de registro para los host personalizados que implementan estas interfaces, debe especificar otra ruta de acceso de registro.</span><span class="sxs-lookup"><span data-stu-id="187fb-187">To view log entries for custom hosts that implement these interfaces, you must specify an alternate log path.</span></span>

#### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a><span data-ttu-id="187fb-188">Para habilitar el registro para las aplicaciones que se ejecutan en el contenedor de la aplicación de Windows</span><span class="sxs-lookup"><span data-stu-id="187fb-188">To enable logging for apps running in the Windows app container</span></span>

1. <span data-ttu-id="187fb-189">Habilite una ruta de acceso de registro personalizada, tal y como se describe en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="187fb-189">Enable a custom log path, as described in the previous procedure.</span></span> <span data-ttu-id="187fb-190">De forma predeterminada, las aplicaciones que se ejecutan en el contenedor de la aplicación de Windows tienen acceso limitado al disco duro.</span><span class="sxs-lookup"><span data-stu-id="187fb-190">By default, apps that are running in the Windows app container have limited access to the hard disk.</span></span> <span data-ttu-id="187fb-191">El directorio especificado tendrá acceso de lectura y escritura para todas las aplicaciones del contenedor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="187fb-191">The directory you specify will have read/write access for all apps in the app container.</span></span>

2. <span data-ttu-id="187fb-192">Seleccione la casilla **Habilitar registro envolvente**.</span><span class="sxs-lookup"><span data-stu-id="187fb-192">Select the **Enable immersive logging** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="187fb-193">Este cuadro solo está habilitada en Windows 8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="187fb-193">This box is enabled only on Windows 8 or later.</span></span>

## <a name="see-also"></a><span data-ttu-id="187fb-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="187fb-194">See also</span></span>

- <xref:System.TypeLoadException>
- [<span data-ttu-id="187fb-195">Herramientas</span><span class="sxs-lookup"><span data-stu-id="187fb-195">Tools</span></span>](index.md)
- [<span data-ttu-id="187fb-196">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="187fb-196">Global Assembly Cache</span></span>](../app-domains/gac.md)
- [<span data-ttu-id="187fb-197">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="187fb-197">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="187fb-198">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="187fb-198">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
