---
title: Diagnóstico de errores con asistentes para la depuración administrada
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
ms.openlocfilehash: 712fbbe9e0ad291385e8eef321c5e8a2fa092a5d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216555"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="95808-102">Diagnóstico de errores con asistentes para la depuración administrada</span><span class="sxs-lookup"><span data-stu-id="95808-102">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="95808-103">Los asistentes de depuración administrada (MDA) son ayudas para la depuración que funcionan en conjunción con Common Language Runtime (CLR) para proporcionar información sobre estado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="95808-103">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="95808-104">Los asistentes generan mensajes informativos sobre eventos en tiempo de ejecución que de otra forma no pueden interceptar.</span><span class="sxs-lookup"><span data-stu-id="95808-104">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="95808-105">Puede utilizar MDA para aislar errores de la aplicación difíciles de encontrar que aparecen al realizar la transición entre código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="95808-105">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="95808-106">Puede [habilitar o deshabilitar](#enable-and-disable-mdas) todos los MDA agregando una clave al registro de Windows o estableciendo una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="95808-106">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="95808-107">Puede habilitar MDA específicos mediante los valores de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95808-107">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="95808-108">Puede establecer opciones de configuración adicionales para algunos MDA concretos en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95808-108">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="95808-109">Dado que estos archivos de configuración se analizan cuando se carga el motor en tiempo de ejecución, debe habilitar el MDA antes de que se inicie la aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="95808-109">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="95808-110">No puede habilitarlo para aplicaciones que ya se han iniciado.</span><span class="sxs-lookup"><span data-stu-id="95808-110">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="95808-111">En la tabla siguiente se enumeran los MDA que se incluyen con el .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="95808-111">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="95808-112">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="95808-112">asynchronousThreadAbort</span></span>](asynchronousthreadabort-mda.md)|[<span data-ttu-id="95808-113">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="95808-113">bindingFailure</span></span>](bindingfailure-mda.md)|
|[<span data-ttu-id="95808-114">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="95808-114">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="95808-115">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="95808-115">contextSwitchDeadlock</span></span>](contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="95808-116">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="95808-116">dangerousThreadingAPI</span></span>](dangerousthreadingapi-mda.md)|[<span data-ttu-id="95808-117">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="95808-117">dateTimeInvalidLocalFormat</span></span>](datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="95808-118">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="95808-118">dirtyCastAndCallOnInterface</span></span>](dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="95808-119">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="95808-119">disconnectedContext</span></span>](disconnectedcontext-mda.md)|
|[<span data-ttu-id="95808-120">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="95808-120">dllMainReturnsFalse</span></span>](dllmainreturnsfalse-mda.md)|[<span data-ttu-id="95808-121">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="95808-121">exceptionSwallowedOnCallFromCom</span></span>](exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="95808-122">failedQI</span><span class="sxs-lookup"><span data-stu-id="95808-122">failedQI</span></span>](failedqi-mda.md)|[<span data-ttu-id="95808-123">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="95808-123">fatalExecutionEngineError</span></span>](fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="95808-124">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="95808-124">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="95808-125">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="95808-125">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="95808-126">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="95808-126">illegalPrepareConstrainedRegion</span></span>](illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="95808-127">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="95808-127">invalidApartmentStateChange</span></span>](invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="95808-128">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="95808-128">invalidCERCall</span></span>](invalidcercall-mda.md)|[<span data-ttu-id="95808-129">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="95808-129">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="95808-130">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="95808-130">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)|[<span data-ttu-id="95808-131">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="95808-131">invalidIUnknown</span></span>](invalidiunknown-mda.md)|
|[<span data-ttu-id="95808-132">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="95808-132">invalidMemberDeclaration</span></span>](invalidmemberdeclaration-mda.md)|[<span data-ttu-id="95808-133">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="95808-133">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="95808-134">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="95808-134">invalidVariant</span></span>](invalidvariant-mda.md)|[<span data-ttu-id="95808-135">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="95808-135">jitCompilationStart</span></span>](jitcompilationstart-mda.md)|
|[<span data-ttu-id="95808-136">loaderLock</span><span class="sxs-lookup"><span data-stu-id="95808-136">loaderLock</span></span>](loaderlock-mda.md)|[<span data-ttu-id="95808-137">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="95808-137">loadFromContext</span></span>](loadfromcontext-mda.md)|
|[<span data-ttu-id="95808-138">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="95808-138">marshalCleanupError</span></span>](marshalcleanuperror-mda.md)|[<span data-ttu-id="95808-139">marshaling</span><span class="sxs-lookup"><span data-stu-id="95808-139">marshaling</span></span>](marshaling-mda.md)|
|[<span data-ttu-id="95808-140">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="95808-140">memberInfoCacheCreation</span></span>](memberinfocachecreation-mda.md)|[<span data-ttu-id="95808-141">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="95808-141">moduloObjectHashcode</span></span>](moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="95808-142">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="95808-142">nonComVisibleBaseClass</span></span>](noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="95808-143">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="95808-143">notMarshalable</span></span>](notmarshalable-mda.md)|
|[<span data-ttu-id="95808-144">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="95808-144">openGenericCERCall</span></span>](opengenericcercall-mda.md)|[<span data-ttu-id="95808-145">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="95808-145">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)|
|[<span data-ttu-id="95808-146">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="95808-146">pInvokeLog</span></span>](pinvokelog-mda.md)|[<span data-ttu-id="95808-147">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="95808-147">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="95808-148">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="95808-148">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)|[<span data-ttu-id="95808-149">reentrancy</span><span class="sxs-lookup"><span data-stu-id="95808-149">reentrancy</span></span>](reentrancy-mda.md)|
|[<span data-ttu-id="95808-150">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="95808-150">releaseHandleFailed</span></span>](releasehandlefailed-mda.md)|[<span data-ttu-id="95808-151">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="95808-151">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)|
|[<span data-ttu-id="95808-152">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="95808-152">streamWriterBufferedDataLost</span></span>](streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="95808-153">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="95808-153">virtualCERCall</span></span>](virtualcercall-mda.md)|

<span data-ttu-id="95808-154">De forma predeterminada, .NET Framework activa un subconjunto de MDA para todos los depuradores administrados.</span><span class="sxs-lookup"><span data-stu-id="95808-154">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="95808-155">Para ver el conjunto predeterminado en Visual Studio, elija **configuración de excepciones** de **Windows** > en el menú **depurar** y, a continuación, expanda la lista **asistentes para la depuración administrada** .</span><span class="sxs-lookup"><span data-stu-id="95808-155">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Ventana Configuración de excepciones en Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="95808-157">Habilitar y deshabilitar MDA</span><span class="sxs-lookup"><span data-stu-id="95808-157">Enable and Disable MDAs</span></span>

<span data-ttu-id="95808-158">Puede habilitar y deshabilitar los MDA mediante una clave del Registro, una variable de entorno o valores de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95808-158">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="95808-159">La clave del Registro o la variable de entorno tienen que estar habilitadas para utilizar los valores de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95808-159">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="95808-160">En lugar de deshabilitar los MDA, puede impedir que Visual Studio muestre el cuadro de diálogo MDA cada vez que se reciba una notificación de MDA.</span><span class="sxs-lookup"><span data-stu-id="95808-160">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="95808-161">Para ello, elija **configuración de excepciones** de **Windows** > en el menú **depurar** , expanda la lista asistentes para la **depuración administrada** y, a continuación, Active o desactive la casilla **interrumpir cuando se produzca** la activación del MDA individual.</span><span class="sxs-lookup"><span data-stu-id="95808-161">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="95808-162">Clave del Registro</span><span class="sxs-lookup"><span data-stu-id="95808-162">Registry Key</span></span>

<span data-ttu-id="95808-163">Para habilitar los MDA, agregue el **HKEY_LOCAL_MACHINE \software\microsoft\\.** Subclave NETFramework\MDA (de tipo REG_SZ, valor 1) en el registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="95808-163">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="95808-164">Copie el ejemplo siguiente en un archivo de texto denominado *MDAEnable. reg*. Abra el editor del registro de Windows (regedit. exe) y, en el menú **archivo** , elija **importar**.</span><span class="sxs-lookup"><span data-stu-id="95808-164">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="95808-165">Seleccione el archivo *MDAEnable. reg* para habilitar los MDA en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="95808-165">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="95808-166">Si se establece la subclave en **un** valor de cadena de 1 (no el valor DWORD de **1**), se habilita la lectura de la configuración de MDA del archivo *applicationName. Suffix*. MDA. config.</span><span class="sxs-lookup"><span data-stu-id="95808-166">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="95808-167">Por ejemplo, el archivo de configuración de MDA para el Bloc de notas se denominará Notepad. exe. MDA. config.</span><span class="sxs-lookup"><span data-stu-id="95808-167">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="95808-168">Si el equipo ejecuta una aplicación de 32 bits en un sistema operativo de 64 bits, la clave de MDA debe establecerse de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="95808-168">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="95808-169">Consulte [valores de configuración específicos de la aplicación](#application-specific-configuration-settings) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="95808-169">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="95808-170">La variable de entorno COMPLUS_MDA puede invalidar la configuración del Registro.</span><span class="sxs-lookup"><span data-stu-id="95808-170">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="95808-171">Consulte [variable de entorno](#environment-variable) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="95808-171">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="95808-172">Para deshabilitar los MDA, establezca la subclave MDA en **0** (cero) mediante el editor del registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="95808-172">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="95808-173">De forma predeterminada, algunos MDA están habilitados cuando se ejecuta una aplicación asociada a un depurador, incluso sin agregar la clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="95808-173">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="95808-174">Puede deshabilitar estos asistentes ejecutando el archivo *MDADisable. reg* como se describió anteriormente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="95808-174">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="95808-175">Variable de entorno</span><span class="sxs-lookup"><span data-stu-id="95808-175">Environment Variable</span></span>

<span data-ttu-id="95808-176">La activación de MDA también puede controlarse mediante la variable de entorno COMPLUS_MDA, que reemplaza la clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="95808-176">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="95808-177">La cadena COMPLUS_MDA es una lista delimitada por puntos y comas de nombres de MDA u otras cadenas de control especiales, y no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="95808-177">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="95808-178">Al iniciar bajo un depurador administrado o no administrado se habilita de forma predeterminada un conjunto de MDA.</span><span class="sxs-lookup"><span data-stu-id="95808-178">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="95808-179">Esto se realiza anteponiendo implícitamente al valor de la variable de entorno o de la clave del Registro la lista delimitada por puntos y comas de los MDA habilitados de manera predeterminada bajo depuradores.</span><span class="sxs-lookup"><span data-stu-id="95808-179">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="95808-180">Las cadenas de control especiales son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="95808-180">The special control strings are the following:</span></span>

- <span data-ttu-id="95808-181">`0` - Desactiva todos los MDA.</span><span class="sxs-lookup"><span data-stu-id="95808-181">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="95808-182">`1`: lee la configuración de MDA de *NombreAplicación*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="95808-182">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="95808-183">`managedDebugger` - Activa explícitamente todos los MDA que se activan implícitamente cuando se inicia un ejecutable administrado bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="95808-183">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="95808-184">`unmanagedDebugger` - Activa explícitamente todos los MDA que se activan implícitamente cuando se inicia un ejecutable no administrado bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="95808-184">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="95808-185">Si hay ajustes contradictorios, los más recientes reemplazan los ajustes anteriores:</span><span class="sxs-lookup"><span data-stu-id="95808-185">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="95808-186">`COMPLUS_MDA=0` deshabilita todos los MDA, incluidos los habilitados implícitamente bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="95808-186">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="95808-187">`COMPLUS_MDA=gcUnmanagedToManaged` habilita `gcUnmanagedToManaged` además de los MDA habilitados implícitamente bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="95808-187">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="95808-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` habilita `gcUnmanagedToManaged` pero deshabilita los MDA que, de otro modo, estarían habilitados implícitamente bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="95808-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="95808-189">Opciones de configuración específicas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="95808-189">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="95808-190">Puede habilitar, deshabilitar y configurar individualmente algunos asistentes en el archivo de configuración de MDA para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95808-190">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="95808-191">Para habilitar el uso de un archivo de configuración de la aplicación para configurar los MDA, es necesario establecer la clave del Registro MDA o la variable de entorno COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="95808-191">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="95808-192">El archivo de configuración de la aplicación se encuentra normalmente en el mismo directorio que el archivo ejecutable (.exe) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95808-192">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="95808-193">El nombre de archivo toma el formato *applicationName*. MDA. config; por ejemplo, Notepad. exe. MDA. config. Los asistentes que están habilitados en el archivo de configuración de la aplicación pueden tener atributos o elementos específicamente diseñados para controlar el comportamiento del asistente.</span><span class="sxs-lookup"><span data-stu-id="95808-193">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="95808-194">En el ejemplo siguiente se muestra cómo habilitar y configurar el [cálculo de referencias](marshaling-mda.md):</span><span class="sxs-lookup"><span data-stu-id="95808-194">The following example shows how to enable and configure the [marshaling](marshaling-mda.md):</span></span>

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

<span data-ttu-id="95808-195">El MDA de `Marshaling` emite información sobre el tipo administrado cuyas referencias se calculan a un tipo no administrado para cada transición de administrado a no administrado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95808-195">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="95808-196">El MDA de `Marshaling` también puede filtrar los nombres de los campos de método y estructura proporcionados en los elementos secundarios **methodFilter** y **fieldFilter** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="95808-196">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="95808-197">En el ejemplo siguiente se muestra cómo habilitar varios MDA mediante su configuración predeterminada:</span><span class="sxs-lookup"><span data-stu-id="95808-197">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> <span data-ttu-id="95808-198">Cuando se especifica más de un asistente en un archivo de configuración, se deben enumerar en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="95808-198">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="95808-199">Por ejemplo, si se desea habilitar los MDA `virtualCERCall` e `invalidCERCall`, se debe agregar la entrada `<invalidCERCall />` antes que la entrada `<virtualCERCall />`.</span><span class="sxs-lookup"><span data-stu-id="95808-199">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="95808-200">Si las entradas no están en orden alfabético, se muestra un mensaje de excepción no controlada de archivo de configuración no válido.</span><span class="sxs-lookup"><span data-stu-id="95808-200">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="95808-201">Excepciones de MDA</span><span class="sxs-lookup"><span data-stu-id="95808-201">MDA exceptions</span></span>

<span data-ttu-id="95808-202">Cuando se habilita un MDA, está activo incluso cuando el código no se está ejecutando en un depurador.</span><span class="sxs-lookup"><span data-stu-id="95808-202">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="95808-203">Si se genera un evento MDA cuando un depurador no está presente, el mensaje del evento se presenta en un cuadro de diálogo de excepción no controlada, aunque no se trata de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="95808-203">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="95808-204">Para evitar el cuadro de diálogo, quite las opciones que habilitan MDA cuando el código no se está ejecutando en un entorno de depuración.</span><span class="sxs-lookup"><span data-stu-id="95808-204">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="95808-205">Cuando el código se ejecuta en el entorno de desarrollo integrado (IDE) de Visual Studio, puede evitar el cuadro de diálogo de excepción que aparece para determinados eventos de MDA.</span><span class="sxs-lookup"><span data-stu-id="95808-205">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="95808-206">Para ello, en el menú **depurar** , elija **configuración de excepciones**de > de **Windows** .</span><span class="sxs-lookup"><span data-stu-id="95808-206">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="95808-207">En la ventana **configuración de excepciones** , expanda la lista asistentes para la **depuración administrada** y, a continuación, desactive la casilla **interrumpir cuando se produzca** el MDA individual.</span><span class="sxs-lookup"><span data-stu-id="95808-207">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="95808-208">También puede utilizar este cuadro de diálogo para *Habilitar* la presentación de los cuadros de diálogo de excepción de MDA.</span><span class="sxs-lookup"><span data-stu-id="95808-208">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="95808-209">Salida del MDA</span><span class="sxs-lookup"><span data-stu-id="95808-209">MDA Output</span></span>

<span data-ttu-id="95808-210">La salida del MDA es similar al ejemplo siguiente, que muestra la salida del MDA `PInvokeStackImbalance`:</span><span class="sxs-lookup"><span data-stu-id="95808-210">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="95808-211">**Una llamada a la función PInvoke ' MDATest! MDATest. Program:: StdCall ' ha desequilibrado la pila. Probablemente, esto se debe a que la firma de PInvoke administrada no coincide con la firma de destino no administrada. Compruebe que la Convención de llamada y los parámetros de la firma PInvoke coinciden con la firma no administrada de destino.**</span><span class="sxs-lookup"><span data-stu-id="95808-211">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="95808-212">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95808-212">See also</span></span>

- [<span data-ttu-id="95808-213">Depurar, trazar y generar perfiles</span><span class="sxs-lookup"><span data-stu-id="95808-213">Debugging, Tracing, and Profiling</span></span>](index.md)
