---
title: Diagnóstico de errores con asistentes de depuraciones administradas
description: Diagnostique errores en .NET con asistentes para la depuración administrada. Los MDA son ayudas para la depuración que funcionan junto con CLR para proporcionar información de estado en tiempo de ejecución.
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
ms.openlocfilehash: ac6fdc09fb057cc55659ce076d37ab96fe2354d1
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416101"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="2f6ec-104">Diagnóstico de errores con asistentes para la depuración administrada</span><span class="sxs-lookup"><span data-stu-id="2f6ec-104">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="2f6ec-105">Los asistentes de depuración administrada (MDA) son ayudas para la depuración que funcionan en conjunción con Common Language Runtime (CLR) para proporcionar información sobre estado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-105">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="2f6ec-106">Los asistentes generan mensajes informativos sobre eventos en tiempo de ejecución que de otra forma no pueden interceptar.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-106">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="2f6ec-107">Puede utilizar MDA para aislar errores de la aplicación difíciles de encontrar que aparecen al realizar la transición entre código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-107">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="2f6ec-108">Puede [habilitar o deshabilitar](#enable-and-disable-mdas) todos los MDA agregando una clave al registro de Windows o estableciendo una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-108">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="2f6ec-109">Puede habilitar MDA específicos mediante los valores de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-109">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="2f6ec-110">Puede establecer opciones de configuración adicionales para algunos MDA concretos en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-110">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="2f6ec-111">Dado que estos archivos de configuración se analizan cuando se carga el motor en tiempo de ejecución, debe habilitar el MDA antes de que se inicie la aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-111">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="2f6ec-112">No puede habilitarlo para aplicaciones que ya se han iniciado.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-112">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="2f6ec-113">En la tabla siguiente se enumeran los MDA que se incluyen con el .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-113">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="2f6ec-114">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="2f6ec-114">asynchronousThreadAbort</span></span>](asynchronousthreadabort-mda.md)|[<span data-ttu-id="2f6ec-115">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="2f6ec-115">bindingFailure</span></span>](bindingfailure-mda.md)|
|[<span data-ttu-id="2f6ec-116">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="2f6ec-116">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="2f6ec-117">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="2f6ec-117">contextSwitchDeadlock</span></span>](contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="2f6ec-118">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="2f6ec-118">dangerousThreadingAPI</span></span>](dangerousthreadingapi-mda.md)|[<span data-ttu-id="2f6ec-119">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="2f6ec-119">dateTimeInvalidLocalFormat</span></span>](datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="2f6ec-120">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="2f6ec-120">dirtyCastAndCallOnInterface</span></span>](dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="2f6ec-121">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="2f6ec-121">disconnectedContext</span></span>](disconnectedcontext-mda.md)|
|[<span data-ttu-id="2f6ec-122">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="2f6ec-122">dllMainReturnsFalse</span></span>](dllmainreturnsfalse-mda.md)|[<span data-ttu-id="2f6ec-123">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="2f6ec-123">exceptionSwallowedOnCallFromCom</span></span>](exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="2f6ec-124">failedQI</span><span class="sxs-lookup"><span data-stu-id="2f6ec-124">failedQI</span></span>](failedqi-mda.md)|[<span data-ttu-id="2f6ec-125">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="2f6ec-125">fatalExecutionEngineError</span></span>](fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="2f6ec-126">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="2f6ec-126">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="2f6ec-127">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="2f6ec-127">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="2f6ec-128">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="2f6ec-128">illegalPrepareConstrainedRegion</span></span>](illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="2f6ec-129">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="2f6ec-129">invalidApartmentStateChange</span></span>](invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="2f6ec-130">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="2f6ec-130">invalidCERCall</span></span>](invalidcercall-mda.md)|[<span data-ttu-id="2f6ec-131">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="2f6ec-131">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="2f6ec-132">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="2f6ec-132">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)|[<span data-ttu-id="2f6ec-133">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="2f6ec-133">invalidIUnknown</span></span>](invalidiunknown-mda.md)|
|[<span data-ttu-id="2f6ec-134">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="2f6ec-134">invalidMemberDeclaration</span></span>](invalidmemberdeclaration-mda.md)|[<span data-ttu-id="2f6ec-135">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="2f6ec-135">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="2f6ec-136">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="2f6ec-136">invalidVariant</span></span>](invalidvariant-mda.md)|[<span data-ttu-id="2f6ec-137">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="2f6ec-137">jitCompilationStart</span></span>](jitcompilationstart-mda.md)|
|[<span data-ttu-id="2f6ec-138">loaderLock</span><span class="sxs-lookup"><span data-stu-id="2f6ec-138">loaderLock</span></span>](loaderlock-mda.md)|[<span data-ttu-id="2f6ec-139">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="2f6ec-139">loadFromContext</span></span>](loadfromcontext-mda.md)|
|[<span data-ttu-id="2f6ec-140">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="2f6ec-140">marshalCleanupError</span></span>](marshalcleanuperror-mda.md)|[<span data-ttu-id="2f6ec-141">marshaling</span><span class="sxs-lookup"><span data-stu-id="2f6ec-141">marshaling</span></span>](marshaling-mda.md)|
|[<span data-ttu-id="2f6ec-142">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="2f6ec-142">memberInfoCacheCreation</span></span>](memberinfocachecreation-mda.md)|[<span data-ttu-id="2f6ec-143">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="2f6ec-143">moduloObjectHashcode</span></span>](moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="2f6ec-144">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="2f6ec-144">nonComVisibleBaseClass</span></span>](noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="2f6ec-145">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="2f6ec-145">notMarshalable</span></span>](notmarshalable-mda.md)|
|[<span data-ttu-id="2f6ec-146">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="2f6ec-146">openGenericCERCall</span></span>](opengenericcercall-mda.md)|[<span data-ttu-id="2f6ec-147">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="2f6ec-147">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)|
|[<span data-ttu-id="2f6ec-148">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="2f6ec-148">pInvokeLog</span></span>](pinvokelog-mda.md)|[<span data-ttu-id="2f6ec-149">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="2f6ec-149">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="2f6ec-150">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="2f6ec-150">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)|[<span data-ttu-id="2f6ec-151">entrar</span><span class="sxs-lookup"><span data-stu-id="2f6ec-151">reentrancy</span></span>](reentrancy-mda.md)|
|[<span data-ttu-id="2f6ec-152">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="2f6ec-152">releaseHandleFailed</span></span>](releasehandlefailed-mda.md)|[<span data-ttu-id="2f6ec-153">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="2f6ec-153">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)|
|[<span data-ttu-id="2f6ec-154">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="2f6ec-154">streamWriterBufferedDataLost</span></span>](streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="2f6ec-155">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="2f6ec-155">virtualCERCall</span></span>](virtualcercall-mda.md)|

<span data-ttu-id="2f6ec-156">De forma predeterminada, .NET Framework activa un subconjunto de MDA para todos los depuradores administrados.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-156">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="2f6ec-157">Para ver el conjunto predeterminado en Visual Studio, elija **Windows**  >  **configuración de excepciones** de Windows en el menú **depurar** y, a continuación, expanda la lista **asistentes para la depuración administrada** .</span><span class="sxs-lookup"><span data-stu-id="2f6ec-157">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Ventana Configuración de excepciones en Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="2f6ec-159">Habilitar y deshabilitar MDA</span><span class="sxs-lookup"><span data-stu-id="2f6ec-159">Enable and Disable MDAs</span></span>

<span data-ttu-id="2f6ec-160">Puede habilitar y deshabilitar los MDA mediante una clave del Registro, una variable de entorno o valores de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-160">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="2f6ec-161">La clave del Registro o la variable de entorno tienen que estar habilitadas para utilizar los valores de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-161">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="2f6ec-162">En lugar de deshabilitar los MDA, puede impedir que Visual Studio muestre el cuadro de diálogo MDA cada vez que se reciba una notificación de MDA.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-162">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="2f6ec-163">Para ello, elija **Windows**  >  **configuración de excepciones** de Windows en el menú **depurar** , expanda la lista asistentes para la **depuración administrada** y, a continuación, Active o desactive la casilla **interrumpir cuando se produzca** la activación del MDA individual.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-163">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="2f6ec-164">Clave del Registro</span><span class="sxs-lookup"><span data-stu-id="2f6ec-164">Registry Key</span></span>

<span data-ttu-id="2f6ec-165">Para habilitar los MDA, agregue el \*\*HKEY_LOCAL_MACHINE \Software\Microsoft \\ . \*\*Subclave NETFramework\MDA (de tipo REG_SZ, valor 1) en el registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-165">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="2f6ec-166">Copie el ejemplo siguiente en un archivo de texto denominado *MDAEnable. reg*. Abra el editor del registro de Windows (RegEdit.exe) y, en el menú **archivo** , elija **importar**.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-166">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="2f6ec-167">Seleccione el archivo *MDAEnable. reg* para habilitar los MDA en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-167">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="2f6ec-168">Si se establece la subclave en **un** valor de cadena de 1 (no el valor DWORD de **1**), se habilita la lectura de la configuración de MDA del archivo *applicationName. Suffix*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-168">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="2f6ec-169">Por ejemplo, el archivo de configuración de MDA para el Bloc de notas se denominará notepad.exe.mda.config.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-169">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="2f6ec-170">Si el equipo ejecuta una aplicación de 32 bits en un sistema operativo de 64 bits, la clave de MDA debe establecerse de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-170">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="2f6ec-171">Consulte [valores de configuración específicos de la aplicación](#application-specific-configuration-settings) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-171">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="2f6ec-172">La variable de entorno COMPLUS_MDA puede invalidar la configuración del Registro.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-172">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="2f6ec-173">Consulte [variable de entorno](#environment-variable) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-173">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="2f6ec-174">Para deshabilitar los MDA, establezca la subclave MDA en **0** (cero) mediante el editor del registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-174">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="2f6ec-175">De forma predeterminada, algunos MDA están habilitados cuando se ejecuta una aplicación asociada a un depurador, incluso sin agregar la clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-175">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="2f6ec-176">Puede deshabilitar estos asistentes ejecutando el archivo *MDADisable. reg* como se describió anteriormente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-176">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="2f6ec-177">Variable de entorno</span><span class="sxs-lookup"><span data-stu-id="2f6ec-177">Environment Variable</span></span>

<span data-ttu-id="2f6ec-178">La activación de MDA también puede controlarse mediante la variable de entorno COMPLUS_MDA, que reemplaza la clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-178">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="2f6ec-179">La cadena COMPLUS_MDA es una lista delimitada por puntos y comas de nombres de MDA u otras cadenas de control especiales, y no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-179">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="2f6ec-180">Al iniciar bajo un depurador administrado o no administrado se habilita de forma predeterminada un conjunto de MDA.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-180">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="2f6ec-181">Esto se realiza anteponiendo implícitamente al valor de la variable de entorno o de la clave del Registro la lista delimitada por puntos y comas de los MDA habilitados de manera predeterminada bajo depuradores.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-181">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="2f6ec-182">Las cadenas de control especiales son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-182">The special control strings are the following:</span></span>

- <span data-ttu-id="2f6ec-183">`0` - Desactiva todos los MDA.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-183">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="2f6ec-184">`1`: lee la configuración de MDA de *NombreAplicación*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-184">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="2f6ec-185">`managedDebugger` - Activa explícitamente todos los MDA que se activan implícitamente cuando se inicia un ejecutable administrado bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-185">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="2f6ec-186">`unmanagedDebugger` - Activa explícitamente todos los MDA que se activan implícitamente cuando se inicia un ejecutable no administrado bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-186">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="2f6ec-187">Si hay ajustes contradictorios, los más recientes reemplazan los ajustes anteriores:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-187">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="2f6ec-188">`COMPLUS_MDA=0` deshabilita todos los MDA, incluidos los habilitados implícitamente bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-188">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="2f6ec-189">`COMPLUS_MDA=gcUnmanagedToManaged` habilita `gcUnmanagedToManaged` además de los MDA habilitados implícitamente bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-189">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="2f6ec-190">`COMPLUS_MDA=0;gcUnmanagedToManaged` habilita `gcUnmanagedToManaged` pero deshabilita los MDA que, de otro modo, estarían habilitados implícitamente bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-190">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="2f6ec-191">Opciones de configuración específicas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="2f6ec-191">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="2f6ec-192">Puede habilitar, deshabilitar y configurar individualmente algunos asistentes en el archivo de configuración de MDA para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-192">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="2f6ec-193">Para habilitar el uso de un archivo de configuración de la aplicación para configurar los MDA, es necesario establecer la clave del Registro MDA o la variable de entorno COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-193">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="2f6ec-194">El archivo de configuración de la aplicación se encuentra normalmente en el mismo directorio que el archivo ejecutable (.exe) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-194">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="2f6ec-195">El nombre de archivo toma el formato *ApplicationName*.mda.config; por ejemplo, notepad.exe.mda.config. Los asistentes que están habilitados en el archivo de configuración de la aplicación pueden tener atributos o elementos específicamente diseñados para controlar el comportamiento del asistente.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-195">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="2f6ec-196">En el ejemplo siguiente se muestra cómo habilitar y configurar el [cálculo de referencias](marshaling-mda.md):</span><span class="sxs-lookup"><span data-stu-id="2f6ec-196">The following example shows how to enable and configure the [marshaling](marshaling-mda.md):</span></span>

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

<span data-ttu-id="2f6ec-197">El MDA de `Marshaling` emite información sobre el tipo administrado cuyas referencias se calculan a un tipo no administrado para cada transición de administrado a no administrado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-197">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="2f6ec-198">El `Marshaling` MDA también puede filtrar los nombres de los campos de método y estructura proporcionados en los elementos secundarios **MethodFilter** y **fieldFilter** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-198">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="2f6ec-199">En el ejemplo siguiente se muestra cómo habilitar varios MDA mediante su configuración predeterminada:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-199">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

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
> <span data-ttu-id="2f6ec-200">Cuando se especifica más de un asistente en un archivo de configuración, se deben enumerar en orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-200">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="2f6ec-201">Por ejemplo, si se desea habilitar los MDA `virtualCERCall` e `invalidCERCall`, se debe agregar la entrada `<invalidCERCall />` antes que la entrada `<virtualCERCall />`.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-201">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="2f6ec-202">Si las entradas no están en orden alfabético, se muestra un mensaje de excepción no controlada de archivo de configuración no válido.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-202">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="2f6ec-203">Excepciones de MDA</span><span class="sxs-lookup"><span data-stu-id="2f6ec-203">MDA exceptions</span></span>

<span data-ttu-id="2f6ec-204">Cuando se habilita un MDA, está activo incluso cuando el código no se está ejecutando en un depurador.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-204">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="2f6ec-205">Si se genera un evento MDA cuando un depurador no está presente, el mensaje del evento se presenta en un cuadro de diálogo de excepción no controlada, aunque no se trata de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-205">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="2f6ec-206">Para evitar el cuadro de diálogo, quite las opciones que habilitan MDA cuando el código no se está ejecutando en un entorno de depuración.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-206">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="2f6ec-207">Cuando el código se ejecuta en el entorno de desarrollo integrado (IDE) de Visual Studio, puede evitar el cuadro de diálogo de excepción que aparece para determinados eventos de MDA.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-207">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="2f6ec-208">Para ello, en el menú **depurar** , elija Configuración de excepciones de **Windows**  >  **Exception Settings**.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-208">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="2f6ec-209">En la ventana **configuración de excepciones** , expanda la lista asistentes para la **depuración administrada** y, a continuación, desactive la casilla **interrumpir cuando se produzca** el MDA individual.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-209">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="2f6ec-210">También puede utilizar este cuadro de diálogo para *Habilitar* la presentación de los cuadros de diálogo de excepción de MDA.</span><span class="sxs-lookup"><span data-stu-id="2f6ec-210">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="2f6ec-211">Salida del MDA</span><span class="sxs-lookup"><span data-stu-id="2f6ec-211">MDA Output</span></span>

<span data-ttu-id="2f6ec-212">La salida del MDA es similar al ejemplo siguiente, que muestra la salida del `PInvokeStackImbalance` MDA:</span><span class="sxs-lookup"><span data-stu-id="2f6ec-212">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="2f6ec-213">**Una llamada a la función PInvoke ' MDATest! MDATest. Program:: StdCall ' ha desequilibrado la pila. Probablemente, esto se debe a que la firma de PInvoke administrada no coincide con la firma de destino no administrada. Compruebe que la Convención de llamada y los parámetros de la firma PInvoke coinciden con la firma no administrada de destino.**</span><span class="sxs-lookup"><span data-stu-id="2f6ec-213">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="2f6ec-214">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f6ec-214">See also</span></span>

- [<span data-ttu-id="2f6ec-215">Depurar, trazar y generar perfiles</span><span class="sxs-lookup"><span data-stu-id="2f6ec-215">Debugging, Tracing, and Profiling</span></span>](index.md)
