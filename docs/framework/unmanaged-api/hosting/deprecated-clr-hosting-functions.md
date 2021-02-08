---
description: 'Más información sobre: funciones de hospedaje de CLR en desuso'
title: Funciones de hospedaje de CLR en desuso
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 3d16b5829e29c5c963f4790bbb3be7adcaeedbfc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785671"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="15afa-103">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="15afa-103">Deprecated CLR Hosting Functions</span></span>

<span data-ttu-id="15afa-104">En esta sección se describen las funciones estáticas globales no administradas que usaban versiones anteriores de la API de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="15afa-104">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="15afa-105">A excepción de las funciones de infraestructura ( `_Cor*` funciones), que solo se usan en el .NET Framework, estas funciones han quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="15afa-105">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="15afa-106">Funciones de activación</span><span class="sxs-lookup"><span data-stu-id="15afa-106">Activation functions</span></span>  

 [<span data-ttu-id="15afa-107">ClrCreateManagedInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-107">ClrCreateManagedInstance Function</span></span>](clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="15afa-108">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-108">Deprecated.</span></span> <span data-ttu-id="15afa-109">Crea una instancia del tipo administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="15afa-109">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="15afa-110">CoInitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-110">CoInitializeCor Function</span></span>](coinitializecor-function.md)  
 <span data-ttu-id="15afa-111">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="15afa-111">Obsolete.</span></span> <span data-ttu-id="15afa-112">Para inicializar el Common Language Runtime (CLR), use [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="15afa-112">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="15afa-113">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-113">CoInitializeEE Function</span></span>](coinitializeee-function.md)  
 <span data-ttu-id="15afa-114">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-114">Deprecated.</span></span> <span data-ttu-id="15afa-115">Garantiza que el motor de ejecución de CLR se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="15afa-115">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="15afa-116">Use en su lugar el método [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="15afa-116">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="15afa-117">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-117">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)  
 <span data-ttu-id="15afa-118">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-118">Deprecated.</span></span> <span data-ttu-id="15afa-119">Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión almacenada en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="15afa-119">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="15afa-120">CorBindToRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-120">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)  
 <span data-ttu-id="15afa-121">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-121">Deprecated.</span></span> <span data-ttu-id="15afa-122">Permite a los hosts no administrados cargar CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="15afa-122">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="15afa-123">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-123">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="15afa-124">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-124">Deprecated.</span></span> <span data-ttu-id="15afa-125">Carga el CLR en un proceso utilizando la información de versión que se lee de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="15afa-125">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="15afa-126">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)  
 <span data-ttu-id="15afa-127">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-127">Deprecated.</span></span> <span data-ttu-id="15afa-128">Permite a los hosts no administrados cargar CLR en un proceso y permite establecer marcas para especificar el comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="15afa-128">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="15afa-129">CorBindToRuntimeHost (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-129">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)  
 <span data-ttu-id="15afa-130">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-130">Deprecated.</span></span> <span data-ttu-id="15afa-131">Permite a los hosts cargar una versión especificada de CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="15afa-131">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="15afa-132">GetCORRequiredVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-132">GetCORRequiredVersion Function</span></span>](getcorrequiredversion-function.md)  
 <span data-ttu-id="15afa-133">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-133">Deprecated.</span></span> <span data-ttu-id="15afa-134">Obtiene el número de versión de CLR requerido.</span><span class="sxs-lookup"><span data-stu-id="15afa-134">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="15afa-135">GetCORSystemDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-135">GetCORSystemDirectory Function</span></span>](getcorsystemdirectory-function.md)  
 <span data-ttu-id="15afa-136">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-136">Deprecated.</span></span> <span data-ttu-id="15afa-137">Devuelve el directorio de instalación de CLR que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="15afa-137">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="15afa-138">GetRealProcAddress (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-138">GetRealProcAddress Function</span></span>](getrealprocaddress-function.md)  
 <span data-ttu-id="15afa-139">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-139">Deprecated.</span></span> <span data-ttu-id="15afa-140">Obtiene la dirección de la función especificada que se exporta de la última versión instalada de CLR.</span><span class="sxs-lookup"><span data-stu-id="15afa-140">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="15afa-141">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-141">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="15afa-142">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-142">Deprecated.</span></span> <span data-ttu-id="15afa-143">Obtiene información de versión y directorio sobre el CLR solicitado por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="15afa-143">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="15afa-144">Funciones de versión de CLR</span><span class="sxs-lookup"><span data-stu-id="15afa-144">CLR version functions</span></span>  

 <span data-ttu-id="15afa-145">Las funciones de esta sección devuelven una versión de CLR; no activan el CLR.</span><span class="sxs-lookup"><span data-stu-id="15afa-145">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="15afa-146">GetCORVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-146">GetCORVersion Function</span></span>](getcorversion-function.md)  
 <span data-ttu-id="15afa-147">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-147">Deprecated.</span></span> <span data-ttu-id="15afa-148">Devuelve el número de versión de CLR que se está ejecutando en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="15afa-148">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="15afa-149">GetFileVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-149">GetFileVersion Function</span></span>](getfileversion-function.md)  
 <span data-ttu-id="15afa-150">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-150">Deprecated.</span></span> <span data-ttu-id="15afa-151">Obtiene la información de versión de CLR del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="15afa-151">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="15afa-152">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-152">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)  
 <span data-ttu-id="15afa-153">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-153">Deprecated.</span></span> <span data-ttu-id="15afa-154">Obtiene el número de versión de CLR solicitado por la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="15afa-154">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="15afa-155">Si esa versión no está instalada, obtiene la versión más reciente instalada antes de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="15afa-155">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="15afa-156">GetRequestedRuntimeVersionForCLSID (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-156">GetRequestedRuntimeVersionForCLSID Function</span></span>](getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="15afa-157">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-157">Deprecated.</span></span> <span data-ttu-id="15afa-158">Obtiene la información de versión de CLR adecuada para la clase con el CLSID especificado.</span><span class="sxs-lookup"><span data-stu-id="15afa-158">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="15afa-159">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-159">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)  
 <span data-ttu-id="15afa-160">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-160">Deprecated.</span></span> <span data-ttu-id="15afa-161">Obtiene el número de versión de CLR que está asociado al identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="15afa-161">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="15afa-162">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-162">LockClrVersion Function</span></span>](lockclrversion-function.md)  
 <span data-ttu-id="15afa-163">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-163">Deprecated.</span></span> <span data-ttu-id="15afa-164">Permite al host determinar qué versión de CLR se utilizará en el proceso antes de inicializar explícitamente CLR.</span><span class="sxs-lookup"><span data-stu-id="15afa-164">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="15afa-165">Funciones de hospedaje</span><span class="sxs-lookup"><span data-stu-id="15afa-165">Hosting functions</span></span>  

 [<span data-ttu-id="15afa-166">CallFunctionShim (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-166">CallFunctionShim Function</span></span>](callfunctionshim-function.md)  
 <span data-ttu-id="15afa-167">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-167">Deprecated.</span></span> <span data-ttu-id="15afa-168">Realiza una llamada a la función que tiene el nombre y los parámetros especificados en la biblioteca especificada.</span><span class="sxs-lookup"><span data-stu-id="15afa-168">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="15afa-169">CoEEShutDownCOM (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-169">CoEEShutDownCOM Function</span></span>](coeeshutdowncom-function.md)  
 <span data-ttu-id="15afa-170">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-170">Deprecated.</span></span> <span data-ttu-id="15afa-171">Descarga un ensamblado COM del proceso.</span><span class="sxs-lookup"><span data-stu-id="15afa-171">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="15afa-172">CorExitProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-172">CorExitProcess Function</span></span>](corexitprocess-function.md)  
 <span data-ttu-id="15afa-173">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-173">Deprecated.</span></span> <span data-ttu-id="15afa-174">Cierra el proceso no administrado actual.</span><span class="sxs-lookup"><span data-stu-id="15afa-174">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="15afa-175">CorLaunchApplication (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-175">CorLaunchApplication Function</span></span>](corlaunchapplication-function.md)  
 <span data-ttu-id="15afa-176">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-176">Deprecated.</span></span> <span data-ttu-id="15afa-177">Inicia la aplicación en la ruta de acceso de red especificada, usando los manifiestos especificados y otros datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="15afa-177">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="15afa-178">CorMarkThreadInThreadPool (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-178">CorMarkThreadInThreadPool Function</span></span>](cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="15afa-179">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-179">Deprecated.</span></span> <span data-ttu-id="15afa-180">Marca el subproceso de grupo de subprocesos que se está ejecutando actualmente para la ejecución de código administrado.</span><span class="sxs-lookup"><span data-stu-id="15afa-180">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="15afa-181">A partir de la versión 2,0 de .NET Framework, esta función no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="15afa-181">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="15afa-182">No es necesario y se puede quitar del código.</span><span class="sxs-lookup"><span data-stu-id="15afa-182">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="15afa-183">CoUninitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-183">CoUninitializeCor Function</span></span>](couninitializecor-function.md)  
 <span data-ttu-id="15afa-184">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="15afa-184">Obsolete.</span></span> <span data-ttu-id="15afa-185">CLR no se puede descargar de un proceso.</span><span class="sxs-lookup"><span data-stu-id="15afa-185">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="15afa-186">CoUninitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-186">CoUninitializeEE Function</span></span>](couninitializeee-function.md)  
 <span data-ttu-id="15afa-187">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="15afa-187">Obsolete.</span></span>  
  
 [<span data-ttu-id="15afa-188">CreateDebuggingInterfaceFromVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-188">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="15afa-189">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-189">Deprecated.</span></span> <span data-ttu-id="15afa-190">Crea un objeto [ICorDebug](../debugging/icordebug-interface.md) basado en la información de versión especificada.</span><span class="sxs-lookup"><span data-stu-id="15afa-190">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="15afa-191">CreateICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-191">CreateICeeFileGen Function</span></span>](createiceefilegen-function.md)  
 <span data-ttu-id="15afa-192">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-192">Deprecated.</span></span> <span data-ttu-id="15afa-193">Crea un objeto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="15afa-193">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="15afa-194">DestroyICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-194">DestroyICeeFileGen Function</span></span>](destroyiceefilegen-function.md)  
 <span data-ttu-id="15afa-195">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-195">Deprecated.</span></span> <span data-ttu-id="15afa-196">Destruye un objeto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="15afa-196">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="15afa-197">puntero a la función FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="15afa-197">FExecuteInAppDomainCallback Function Pointer</span></span>](fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="15afa-198">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-198">Deprecated.</span></span> <span data-ttu-id="15afa-199">Apunta a una función a la que CLR llama para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="15afa-199">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="15afa-200">puntero a la función FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="15afa-200">FLockClrVersionCallback Function Pointer</span></span>](flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="15afa-201">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-201">Deprecated.</span></span> <span data-ttu-id="15afa-202">Apunta a una función a la que CLR llama para notificar al host que la inicialización se ha iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="15afa-202">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="15afa-203">GetCLRIdentityManager (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-203">GetCLRIdentityManager Function</span></span>](getclridentitymanager-function.md)  
 <span data-ttu-id="15afa-204">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-204">Deprecated.</span></span> <span data-ttu-id="15afa-205">Obtiene un puntero a una interfaz que permite a CLR administrar las identidades.</span><span class="sxs-lookup"><span data-stu-id="15afa-205">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="15afa-206">LoadLibraryShim (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-206">LoadLibraryShim Function</span></span>](loadlibraryshim-function.md)  
 <span data-ttu-id="15afa-207">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-207">Deprecated.</span></span> <span data-ttu-id="15afa-208">Carga una versión especificada de un .NET Framework DLL.</span><span class="sxs-lookup"><span data-stu-id="15afa-208">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="15afa-209">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-209">LoadStringRC Function</span></span>](loadstringrc-function.md)  
 <span data-ttu-id="15afa-210">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-210">Deprecated.</span></span> <span data-ttu-id="15afa-211">Convierte un valor HRESULT en un mensaje de error utilizando la referencia cultural predeterminada del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="15afa-211">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="15afa-212">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-212">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)  
 <span data-ttu-id="15afa-213">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-213">Deprecated.</span></span> <span data-ttu-id="15afa-214">Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="15afa-214">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="15afa-215">puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="15afa-215">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="15afa-216">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-216">Deprecated.</span></span> <span data-ttu-id="15afa-217">Apunta a una función que notifica al host cuando se ha completado una e/s superpuesta (es decir, asincrónica) a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15afa-217">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="15afa-218">puntero a la función LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="15afa-218">LPTHREAD_START_ROUTINE Function Pointer</span></span>](lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="15afa-219">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-219">Deprecated.</span></span> <span data-ttu-id="15afa-220">Apunta a una función que notifica al host que se ha iniciado la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="15afa-220">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="15afa-221">RunDll32ShimW (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-221">RunDll32ShimW Function</span></span>](rundll32shimw-function.md)  
 <span data-ttu-id="15afa-222">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-222">Deprecated.</span></span> <span data-ttu-id="15afa-223">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="15afa-223">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="15afa-224">puntero a la función WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="15afa-224">WAITORTIMERCALLBACK Function Pointer</span></span>](waitortimercallback-function-pointer.md)  
 <span data-ttu-id="15afa-225">En desuso.</span><span class="sxs-lookup"><span data-stu-id="15afa-225">Deprecated.</span></span> <span data-ttu-id="15afa-226">Apunta a una función que notifica al host que un identificador de espera se ha señalado o ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="15afa-226">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="15afa-227">Funciones de infraestructura</span><span class="sxs-lookup"><span data-stu-id="15afa-227">Infrastructure functions</span></span>  

 <span data-ttu-id="15afa-228">Las funciones de esta sección solo las pueden usar los .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="15afa-228">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="15afa-229">_CorDllMain (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-229">_CorDllMain Function</span></span>](cordllmain-function.md)  
 <span data-ttu-id="15afa-230">Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado de DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="15afa-230">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="15afa-231">_CorExeMain (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-231">_CorExeMain Function</span></span>](corexemain-function.md)  
 <span data-ttu-id="15afa-232">Inicializa CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="15afa-232">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="15afa-233">_CorExeMain2 (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-233">_CorExeMain2 Function</span></span>](corexemain2-function.md)  
 <span data-ttu-id="15afa-234">Ejecuta el punto de entrada en el código asignado a la memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="15afa-234">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="15afa-235">El cargador del sistema operativo llama a esta función.</span><span class="sxs-lookup"><span data-stu-id="15afa-235">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="15afa-236">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-236">_CorImageUnloading Function</span></span>](corimageunloading-function.md)  
 <span data-ttu-id="15afa-237">Notifica al cargador cuando se descargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="15afa-237">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="15afa-238">_CorValidateImage (Función)</span><span class="sxs-lookup"><span data-stu-id="15afa-238">_CorValidateImage Function</span></span>](corvalidateimage-function.md)  
 <span data-ttu-id="15afa-239">Valida las imágenes del módulo administrado y notifica al cargador del sistema operativo una vez que se han cargado.</span><span class="sxs-lookup"><span data-stu-id="15afa-239">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15afa-240">Vea también</span><span class="sxs-lookup"><span data-stu-id="15afa-240">See also</span></span>

- [<span data-ttu-id="15afa-241">Funciones estáticas globales de hospedaje de .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="15afa-241">.NET Framework 4 Hosting Global Static Functions</span></span>](net-framework-4-hosting-global-static-functions.md)
