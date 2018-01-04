---
title: Funciones de hospedaje de CLR en desuso
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 985425ad44003f5971b21f107fad322f2123f6ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="b02c3-102">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="b02c3-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="b02c3-103">Esta sección describen las funciones estáticas globales no administradas que utiliza versiones anteriores de la API de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="b02c3-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="b02c3-104">Con la excepción de las funciones de infraestructura (`_Cor*` funciones), que se usa únicamente con .NET Framework, estas funciones han quedado obsoletas en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b02c3-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="b02c3-105">Funciones de activación</span><span class="sxs-lookup"><span data-stu-id="b02c3-105">Activation functions</span></span>  
 [<span data-ttu-id="b02c3-106">ClrCreateManagedInstance (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="b02c3-107">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-107">Deprecated.</span></span> <span data-ttu-id="b02c3-108">Crea una instancia del tipo administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="b02c3-109">CoInitializeCor (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="b02c3-110">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b02c3-110">Obsolete.</span></span> <span data-ttu-id="b02c3-111">Para inicializar common language runtime (CLR), use [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="b02c3-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="b02c3-112">CoInitializeEE (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="b02c3-113">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-113">Deprecated.</span></span> <span data-ttu-id="b02c3-114">Garantiza que el motor de ejecución de CLR se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="b02c3-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="b02c3-115">Use la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b02c3-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="b02c3-116">CorBindToCurrentRuntime (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="b02c3-117">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-117">Deprecated.</span></span> <span data-ttu-id="b02c3-118">Carga common language runtime (CLR) en un proceso usando la información de versión almacenada en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="b02c3-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="b02c3-119">CorBindToRuntime (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="b02c3-120">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-120">Deprecated.</span></span> <span data-ttu-id="b02c3-121">Permite que los hosts no administrados cargar CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="b02c3-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="b02c3-122">CorBindToRuntimeByCfg (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="b02c3-123">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-123">Deprecated.</span></span> <span data-ttu-id="b02c3-124">Carga el CLR en un proceso mediante el uso de información de versión que se lee desde un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="b02c3-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="b02c3-125">CorBindToRuntimeEx (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="b02c3-126">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-126">Deprecated.</span></span> <span data-ttu-id="b02c3-127">Permite a los hosts no administrados cargar CLR en un proceso y permite establecer marcas para especificar el comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="b02c3-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="b02c3-128">CorBindToRuntimeHost (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="b02c3-129">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-129">Deprecated.</span></span> <span data-ttu-id="b02c3-130">Permite a los hosts cargar una versión especificada de CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="b02c3-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="b02c3-131">GetCORRequiredVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="b02c3-132">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-132">Deprecated.</span></span> <span data-ttu-id="b02c3-133">Obtiene el número de versión CLR necesario.</span><span class="sxs-lookup"><span data-stu-id="b02c3-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="b02c3-134">GetCORSystemDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="b02c3-135">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-135">Deprecated.</span></span> <span data-ttu-id="b02c3-136">Devuelve el directorio de instalación de CLR que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b02c3-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="b02c3-137">GetRealProcAddress (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="b02c3-138">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-138">Deprecated.</span></span> <span data-ttu-id="b02c3-139">Obtiene la dirección de la función especificada que se exporta desde la última versión instalada de CLR.</span><span class="sxs-lookup"><span data-stu-id="b02c3-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="b02c3-140">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="b02c3-141">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-141">Deprecated.</span></span> <span data-ttu-id="b02c3-142">Obtiene información de versión y directorio acerca del entorno CLR solicitado por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b02c3-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="b02c3-143">Funciones de la versión CLR</span><span class="sxs-lookup"><span data-stu-id="b02c3-143">CLR version functions</span></span>  
 <span data-ttu-id="b02c3-144">Las funciones de esta sección devuelven una versión CLR; no activa el CLR.</span><span class="sxs-lookup"><span data-stu-id="b02c3-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="b02c3-145">GetCORVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="b02c3-146">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-146">Deprecated.</span></span> <span data-ttu-id="b02c3-147">Devuelve el número de versión de CLR que se ejecuta en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="b02c3-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="b02c3-148">GetFileVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="b02c3-149">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-149">Deprecated.</span></span> <span data-ttu-id="b02c3-150">Obtiene la información de versión CLR del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="b02c3-151">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="b02c3-152">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-152">Deprecated.</span></span> <span data-ttu-id="b02c3-153">Obtiene el número de versión de CLR solicitado por la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="b02c3-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="b02c3-154">Si no está instalada esa versión, obtiene la versión más reciente que esté instalada antes de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="b02c3-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="b02c3-155">GetRequestedRuntimeVersionForCLSID (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="b02c3-156">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-156">Deprecated.</span></span> <span data-ttu-id="b02c3-157">Obtiene la información de versión CLR correspondiente para la clase con el CLSID especificado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="b02c3-158">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="b02c3-159">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-159">Deprecated.</span></span> <span data-ttu-id="b02c3-160">Obtiene el número de versión de CLR que está asociado con el identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="b02c3-161">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="b02c3-162">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-162">Deprecated.</span></span> <span data-ttu-id="b02c3-163">Permite al host determinar qué versión de CLR se utilizará en el proceso antes de inicializar el CLR de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="b02c3-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="b02c3-164">Funciones de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b02c3-164">Hosting functions</span></span>  
 [<span data-ttu-id="b02c3-165">CallFunctionShim (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="b02c3-166">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-166">Deprecated.</span></span> <span data-ttu-id="b02c3-167">Realiza una llamada a la función que tiene el nombre especificado y los parámetros en la biblioteca especificada.</span><span class="sxs-lookup"><span data-stu-id="b02c3-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="b02c3-168">CoEEShutDownCOM (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="b02c3-169">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-169">Deprecated.</span></span> <span data-ttu-id="b02c3-170">Descarga un ensamblado COM del proceso.</span><span class="sxs-lookup"><span data-stu-id="b02c3-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="b02c3-171">CorExitProcess (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="b02c3-172">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-172">Deprecated.</span></span> <span data-ttu-id="b02c3-173">Se cierra el proceso actual no administrado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="b02c3-174">CorLaunchApplication (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="b02c3-175">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-175">Deprecated.</span></span> <span data-ttu-id="b02c3-176">Inicia la aplicación en la ruta de acceso de red especificada, utilizando los manifiestos especificados y otros datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b02c3-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="b02c3-177">CorMarkThreadInThreadPool (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="b02c3-178">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-178">Deprecated.</span></span> <span data-ttu-id="b02c3-179">Marca el subproceso actualmente en ejecución del grupo de subprocesos para la ejecución de código administrado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="b02c3-180">A partir de la versión 2.0 de .NET Framework, esta función no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="b02c3-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="b02c3-181">No es necesario y puede quitarse desde el código.</span><span class="sxs-lookup"><span data-stu-id="b02c3-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="b02c3-182">CoUninitializeCor (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="b02c3-183">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b02c3-183">Obsolete.</span></span> <span data-ttu-id="b02c3-184">El CLR no se puede descargar desde un proceso.</span><span class="sxs-lookup"><span data-stu-id="b02c3-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="b02c3-185">CoUninitializeEE (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="b02c3-186">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b02c3-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="b02c3-187">CreateDebuggingInterfaceFromVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="b02c3-188">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-188">Deprecated.</span></span> <span data-ttu-id="b02c3-189">Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto basándose en la información de versión especificada.</span><span class="sxs-lookup"><span data-stu-id="b02c3-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="b02c3-190">CreateICeeFileGen (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="b02c3-191">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-191">Deprecated.</span></span> <span data-ttu-id="b02c3-192">Crea un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="b02c3-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="b02c3-193">DestroyICeeFileGen (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="b02c3-194">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-194">Deprecated.</span></span> <span data-ttu-id="b02c3-195">Destruye una [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="b02c3-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="b02c3-196">Puntero a la función FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="b02c3-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="b02c3-197">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-197">Deprecated.</span></span> <span data-ttu-id="b02c3-198">Señala a una función que llama a CLR para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="b02c3-199">Puntero a la función FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="b02c3-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="b02c3-200">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-200">Deprecated.</span></span> <span data-ttu-id="b02c3-201">Señala a una función que CLR llama para notificar al host que la inicialización se ha iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="b02c3-202">GetCLRIdentityManager (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="b02c3-203">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-203">Deprecated.</span></span> <span data-ttu-id="b02c3-204">Obtiene un puntero a una interfaz que permite a CLR administrar identidades.</span><span class="sxs-lookup"><span data-stu-id="b02c3-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="b02c3-205">LoadLibraryShim (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="b02c3-206">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-206">Deprecated.</span></span> <span data-ttu-id="b02c3-207">Carga la versión especificada de una DLL de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b02c3-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="b02c3-208">LoadStringRC (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="b02c3-209">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-209">Deprecated.</span></span> <span data-ttu-id="b02c3-210">Convierte un valor HRESULT en un mensaje de error mediante el uso de la referencia cultural predeterminada del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="b02c3-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="b02c3-211">LoadStringRCEx (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="b02c3-212">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-212">Deprecated.</span></span> <span data-ttu-id="b02c3-213">Convierte un valor HRESULT a un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="b02c3-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="b02c3-214">Puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="b02c3-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="b02c3-215">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-215">Deprecated.</span></span> <span data-ttu-id="b02c3-216">Señala a una función que notifica al host cuándo una superposición (es decir, asincrónica) ha completado la E/S en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b02c3-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="b02c3-217">Puntero a la función LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="b02c3-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="b02c3-218">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-218">Deprecated.</span></span> <span data-ttu-id="b02c3-219">Señala a una función que notifica al host que ha empezado a ejecutar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="b02c3-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="b02c3-220">RunDll32ShimW (Función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="b02c3-221">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-221">Deprecated.</span></span> <span data-ttu-id="b02c3-222">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="b02c3-223">Puntero a la función WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="b02c3-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="b02c3-224">Desusado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-224">Deprecated.</span></span> <span data-ttu-id="b02c3-225">Señala a una función que notifica al host que un identificador de espera se ha señalado o agotó el tiempo.</span><span class="sxs-lookup"><span data-stu-id="b02c3-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="b02c3-226">Funciones de infraestructura</span><span class="sxs-lookup"><span data-stu-id="b02c3-226">Infrastructure functions</span></span>  
 <span data-ttu-id="b02c3-227">Las funciones de esta sección son para uso sólo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b02c3-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="b02c3-228">_CorDllMain (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="b02c3-229">Inicializa el CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado de la DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b02c3-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="b02c3-230">_CorExeMain (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="b02c3-231">Inicializa el CLR, busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b02c3-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="b02c3-232">_CorExeMain2 (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="b02c3-233">Ejecuta el punto de entrada en el código asignado a la memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="b02c3-234">Esta función se invoca por el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b02c3-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="b02c3-235">_CorImageUnloading (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="b02c3-236">Notifica al cargador cuándo se descargan imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="b02c3-237">_CorValidateImage (función)</span><span class="sxs-lookup"><span data-stu-id="b02c3-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="b02c3-238">Valida las imágenes del módulo administrado y notifica el cargador del sistema operativo después de que se han cargado.</span><span class="sxs-lookup"><span data-stu-id="b02c3-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b02c3-239">Vea también</span><span class="sxs-lookup"><span data-stu-id="b02c3-239">See Also</span></span>  
 [<span data-ttu-id="b02c3-240">Funciones estáticas globales de hospedaje de .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="b02c3-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
