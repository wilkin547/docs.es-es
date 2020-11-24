---
title: Funciones de hospedaje de CLR en desuso
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 9e19502672973f292991b72c7ea9b4fdc17f5707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673129"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="c1dab-102">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="c1dab-102">Deprecated CLR Hosting Functions</span></span>

<span data-ttu-id="c1dab-103">En esta sección se describen las funciones estáticas globales no administradas que usaban versiones anteriores de la API de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="c1dab-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="c1dab-104">A excepción de las funciones de infraestructura ( `_Cor*` funciones), que solo se usan en el .NET Framework, estas funciones han quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c1dab-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="c1dab-105">Funciones de activación</span><span class="sxs-lookup"><span data-stu-id="c1dab-105">Activation functions</span></span>  

 [<span data-ttu-id="c1dab-106">ClrCreateManagedInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-106">ClrCreateManagedInstance Function</span></span>](clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="c1dab-107">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-107">Deprecated.</span></span> <span data-ttu-id="c1dab-108">Crea una instancia del tipo administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="c1dab-109">CoInitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-109">CoInitializeCor Function</span></span>](coinitializecor-function.md)  
 <span data-ttu-id="c1dab-110">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c1dab-110">Obsolete.</span></span> <span data-ttu-id="c1dab-111">Para inicializar el Common Language Runtime (CLR), use [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="c1dab-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="c1dab-112">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-112">CoInitializeEE Function</span></span>](coinitializeee-function.md)  
 <span data-ttu-id="c1dab-113">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-113">Deprecated.</span></span> <span data-ttu-id="c1dab-114">Garantiza que el motor de ejecución de CLR se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="c1dab-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="c1dab-115">Use en su lugar el método [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c1dab-115">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="c1dab-116">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-116">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)  
 <span data-ttu-id="c1dab-117">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-117">Deprecated.</span></span> <span data-ttu-id="c1dab-118">Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión almacenada en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="c1dab-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="c1dab-119">CorBindToRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-119">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)  
 <span data-ttu-id="c1dab-120">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-120">Deprecated.</span></span> <span data-ttu-id="c1dab-121">Permite a los hosts no administrados cargar CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="c1dab-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="c1dab-122">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-122">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="c1dab-123">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-123">Deprecated.</span></span> <span data-ttu-id="c1dab-124">Carga el CLR en un proceso utilizando la información de versión que se lee de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="c1dab-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="c1dab-125">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-125">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)  
 <span data-ttu-id="c1dab-126">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-126">Deprecated.</span></span> <span data-ttu-id="c1dab-127">Permite a los hosts no administrados cargar CLR en un proceso y permite establecer marcas para especificar el comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="c1dab-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="c1dab-128">CorBindToRuntimeHost (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)  
 <span data-ttu-id="c1dab-129">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-129">Deprecated.</span></span> <span data-ttu-id="c1dab-130">Permite a los hosts cargar una versión especificada de CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="c1dab-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="c1dab-131">GetCORRequiredVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-131">GetCORRequiredVersion Function</span></span>](getcorrequiredversion-function.md)  
 <span data-ttu-id="c1dab-132">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-132">Deprecated.</span></span> <span data-ttu-id="c1dab-133">Obtiene el número de versión de CLR requerido.</span><span class="sxs-lookup"><span data-stu-id="c1dab-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="c1dab-134">GetCORSystemDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-134">GetCORSystemDirectory Function</span></span>](getcorsystemdirectory-function.md)  
 <span data-ttu-id="c1dab-135">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-135">Deprecated.</span></span> <span data-ttu-id="c1dab-136">Devuelve el directorio de instalación de CLR que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c1dab-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="c1dab-137">GetRealProcAddress (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-137">GetRealProcAddress Function</span></span>](getrealprocaddress-function.md)  
 <span data-ttu-id="c1dab-138">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-138">Deprecated.</span></span> <span data-ttu-id="c1dab-139">Obtiene la dirección de la función especificada que se exporta de la última versión instalada de CLR.</span><span class="sxs-lookup"><span data-stu-id="c1dab-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="c1dab-140">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-140">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="c1dab-141">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-141">Deprecated.</span></span> <span data-ttu-id="c1dab-142">Obtiene información de versión y directorio sobre el CLR solicitado por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="c1dab-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="c1dab-143">Funciones de versión de CLR</span><span class="sxs-lookup"><span data-stu-id="c1dab-143">CLR version functions</span></span>  

 <span data-ttu-id="c1dab-144">Las funciones de esta sección devuelven una versión de CLR; no activan el CLR.</span><span class="sxs-lookup"><span data-stu-id="c1dab-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="c1dab-145">GetCORVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-145">GetCORVersion Function</span></span>](getcorversion-function.md)  
 <span data-ttu-id="c1dab-146">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-146">Deprecated.</span></span> <span data-ttu-id="c1dab-147">Devuelve el número de versión de CLR que se está ejecutando en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="c1dab-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="c1dab-148">GetFileVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-148">GetFileVersion Function</span></span>](getfileversion-function.md)  
 <span data-ttu-id="c1dab-149">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-149">Deprecated.</span></span> <span data-ttu-id="c1dab-150">Obtiene la información de versión de CLR del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="c1dab-151">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-151">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)  
 <span data-ttu-id="c1dab-152">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-152">Deprecated.</span></span> <span data-ttu-id="c1dab-153">Obtiene el número de versión de CLR solicitado por la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="c1dab-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="c1dab-154">Si esa versión no está instalada, obtiene la versión más reciente instalada antes de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="c1dab-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="c1dab-155">GetRequestedRuntimeVersionForCLSID (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="c1dab-156">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-156">Deprecated.</span></span> <span data-ttu-id="c1dab-157">Obtiene la información de versión de CLR adecuada para la clase con el CLSID especificado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="c1dab-158">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-158">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)  
 <span data-ttu-id="c1dab-159">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-159">Deprecated.</span></span> <span data-ttu-id="c1dab-160">Obtiene el número de versión de CLR que está asociado al identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="c1dab-161">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-161">LockClrVersion Function</span></span>](lockclrversion-function.md)  
 <span data-ttu-id="c1dab-162">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-162">Deprecated.</span></span> <span data-ttu-id="c1dab-163">Permite al host determinar qué versión de CLR se utilizará en el proceso antes de inicializar explícitamente CLR.</span><span class="sxs-lookup"><span data-stu-id="c1dab-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="c1dab-164">Funciones de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c1dab-164">Hosting functions</span></span>  

 [<span data-ttu-id="c1dab-165">CallFunctionShim (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-165">CallFunctionShim Function</span></span>](callfunctionshim-function.md)  
 <span data-ttu-id="c1dab-166">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-166">Deprecated.</span></span> <span data-ttu-id="c1dab-167">Realiza una llamada a la función que tiene el nombre y los parámetros especificados en la biblioteca especificada.</span><span class="sxs-lookup"><span data-stu-id="c1dab-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="c1dab-168">CoEEShutDownCOM (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-168">CoEEShutDownCOM Function</span></span>](coeeshutdowncom-function.md)  
 <span data-ttu-id="c1dab-169">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-169">Deprecated.</span></span> <span data-ttu-id="c1dab-170">Descarga un ensamblado COM del proceso.</span><span class="sxs-lookup"><span data-stu-id="c1dab-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="c1dab-171">CorExitProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-171">CorExitProcess Function</span></span>](corexitprocess-function.md)  
 <span data-ttu-id="c1dab-172">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-172">Deprecated.</span></span> <span data-ttu-id="c1dab-173">Cierra el proceso no administrado actual.</span><span class="sxs-lookup"><span data-stu-id="c1dab-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="c1dab-174">CorLaunchApplication (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-174">CorLaunchApplication Function</span></span>](corlaunchapplication-function.md)  
 <span data-ttu-id="c1dab-175">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-175">Deprecated.</span></span> <span data-ttu-id="c1dab-176">Inicia la aplicación en la ruta de acceso de red especificada, usando los manifiestos especificados y otros datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c1dab-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="c1dab-177">CorMarkThreadInThreadPool (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-177">CorMarkThreadInThreadPool Function</span></span>](cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="c1dab-178">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-178">Deprecated.</span></span> <span data-ttu-id="c1dab-179">Marca el subproceso de grupo de subprocesos que se está ejecutando actualmente para la ejecución de código administrado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="c1dab-180">A partir de la versión 2,0 de .NET Framework, esta función no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="c1dab-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="c1dab-181">No es necesario y se puede quitar del código.</span><span class="sxs-lookup"><span data-stu-id="c1dab-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="c1dab-182">CoUninitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-182">CoUninitializeCor Function</span></span>](couninitializecor-function.md)  
 <span data-ttu-id="c1dab-183">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c1dab-183">Obsolete.</span></span> <span data-ttu-id="c1dab-184">CLR no se puede descargar de un proceso.</span><span class="sxs-lookup"><span data-stu-id="c1dab-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="c1dab-185">CoUninitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-185">CoUninitializeEE Function</span></span>](couninitializeee-function.md)  
 <span data-ttu-id="c1dab-186">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c1dab-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="c1dab-187">CreateDebuggingInterfaceFromVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-187">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="c1dab-188">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-188">Deprecated.</span></span> <span data-ttu-id="c1dab-189">Crea un objeto [ICorDebug](../debugging/icordebug-interface.md) basado en la información de versión especificada.</span><span class="sxs-lookup"><span data-stu-id="c1dab-189">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="c1dab-190">CreateICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-190">CreateICeeFileGen Function</span></span>](createiceefilegen-function.md)  
 <span data-ttu-id="c1dab-191">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-191">Deprecated.</span></span> <span data-ttu-id="c1dab-192">Crea un objeto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="c1dab-192">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="c1dab-193">DestroyICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-193">DestroyICeeFileGen Function</span></span>](destroyiceefilegen-function.md)  
 <span data-ttu-id="c1dab-194">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-194">Deprecated.</span></span> <span data-ttu-id="c1dab-195">Destruye un objeto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="c1dab-195">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="c1dab-196">puntero a la función FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="c1dab-196">FExecuteInAppDomainCallback Function Pointer</span></span>](fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="c1dab-197">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-197">Deprecated.</span></span> <span data-ttu-id="c1dab-198">Apunta a una función a la que CLR llama para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="c1dab-199">puntero a la función FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="c1dab-199">FLockClrVersionCallback Function Pointer</span></span>](flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="c1dab-200">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-200">Deprecated.</span></span> <span data-ttu-id="c1dab-201">Apunta a una función a la que CLR llama para notificar al host que la inicialización se ha iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="c1dab-202">GetCLRIdentityManager (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-202">GetCLRIdentityManager Function</span></span>](getclridentitymanager-function.md)  
 <span data-ttu-id="c1dab-203">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-203">Deprecated.</span></span> <span data-ttu-id="c1dab-204">Obtiene un puntero a una interfaz que permite a CLR administrar las identidades.</span><span class="sxs-lookup"><span data-stu-id="c1dab-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="c1dab-205">LoadLibraryShim (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-205">LoadLibraryShim Function</span></span>](loadlibraryshim-function.md)  
 <span data-ttu-id="c1dab-206">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-206">Deprecated.</span></span> <span data-ttu-id="c1dab-207">Carga una versión especificada de un .NET Framework DLL.</span><span class="sxs-lookup"><span data-stu-id="c1dab-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="c1dab-208">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-208">LoadStringRC Function</span></span>](loadstringrc-function.md)  
 <span data-ttu-id="c1dab-209">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-209">Deprecated.</span></span> <span data-ttu-id="c1dab-210">Convierte un valor HRESULT en un mensaje de error utilizando la referencia cultural predeterminada del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c1dab-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="c1dab-211">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-211">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)  
 <span data-ttu-id="c1dab-212">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-212">Deprecated.</span></span> <span data-ttu-id="c1dab-213">Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="c1dab-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="c1dab-214">puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="c1dab-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="c1dab-215">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-215">Deprecated.</span></span> <span data-ttu-id="c1dab-216">Apunta a una función que notifica al host cuando se ha completado una e/s superpuesta (es decir, asincrónica) a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1dab-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="c1dab-217">puntero a la función LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="c1dab-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="c1dab-218">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-218">Deprecated.</span></span> <span data-ttu-id="c1dab-219">Apunta a una función que notifica al host que se ha iniciado la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="c1dab-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="c1dab-220">RunDll32ShimW (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-220">RunDll32ShimW Function</span></span>](rundll32shimw-function.md)  
 <span data-ttu-id="c1dab-221">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-221">Deprecated.</span></span> <span data-ttu-id="c1dab-222">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="c1dab-223">puntero a la función WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="c1dab-223">WAITORTIMERCALLBACK Function Pointer</span></span>](waitortimercallback-function-pointer.md)  
 <span data-ttu-id="c1dab-224">Desusado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-224">Deprecated.</span></span> <span data-ttu-id="c1dab-225">Apunta a una función que notifica al host que un identificador de espera se ha señalado o ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c1dab-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="c1dab-226">Funciones de infraestructura</span><span class="sxs-lookup"><span data-stu-id="c1dab-226">Infrastructure functions</span></span>  

 <span data-ttu-id="c1dab-227">Las funciones de esta sección solo las pueden usar los .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1dab-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="c1dab-228">_CorDllMain (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-228">_CorDllMain Function</span></span>](cordllmain-function.md)  
 <span data-ttu-id="c1dab-229">Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado de DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1dab-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="c1dab-230">_CorExeMain (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-230">_CorExeMain Function</span></span>](corexemain-function.md)  
 <span data-ttu-id="c1dab-231">Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1dab-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="c1dab-232">_CorExeMain2 (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-232">_CorExeMain2 Function</span></span>](corexemain2-function.md)  
 <span data-ttu-id="c1dab-233">Ejecuta el punto de entrada en el código asignado a la memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="c1dab-234">El cargador del sistema operativo llama a esta función.</span><span class="sxs-lookup"><span data-stu-id="c1dab-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="c1dab-235">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-235">_CorImageUnloading Function</span></span>](corimageunloading-function.md)  
 <span data-ttu-id="c1dab-236">Notifica al cargador cuando se descargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="c1dab-237">_CorValidateImage (Función)</span><span class="sxs-lookup"><span data-stu-id="c1dab-237">_CorValidateImage Function</span></span>](corvalidateimage-function.md)  
 <span data-ttu-id="c1dab-238">Valida las imágenes del módulo administrado y notifica al cargador del sistema operativo una vez que se han cargado.</span><span class="sxs-lookup"><span data-stu-id="c1dab-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1dab-239">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1dab-239">See also</span></span>

- [<span data-ttu-id="c1dab-240">Funciones estáticas globales de hospedaje de .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="c1dab-240">.NET Framework 4 Hosting Global Static Functions</span></span>](net-framework-4-hosting-global-static-functions.md)
