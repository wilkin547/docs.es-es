---
description: 'Más información acerca de: función CorBindToRuntimeEx'
title: CorBindToRuntimeEx (Función)
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
ms.openlocfilehash: 64ea90619d13306d8dd78eb231f9f8dbc927913f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717243"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="cfb25-103">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="cfb25-103">CorBindToRuntimeEx Function</span></span>

<span data-ttu-id="cfb25-104">Permite a los hosts no administrados cargar Common Language Runtime (CLR) en un proceso.</span><span class="sxs-lookup"><span data-stu-id="cfb25-104">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="cfb25-105">Las funciones [CorBindToRuntime](corbindtoruntime-function.md) y `CorBindToRuntimeEx` realizan la misma operación, pero la `CorBindToRuntimeEx` función permite establecer marcas para especificar el comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="cfb25-105">The [CorBindToRuntime](corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="cfb25-106">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="cfb25-106">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="cfb25-107">Esta función adopta una serie de parámetros que permiten a un host hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfb25-107">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="cfb25-108">Especificar la versión del runtime que se cargará.</span><span class="sxs-lookup"><span data-stu-id="cfb25-108">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="cfb25-109">Indicar si se debe cargar la compilación para servidor o para estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cfb25-109">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="cfb25-110">Controlar si se realiza una recolección de elementos no utilizados simultánea o no simultánea.</span><span class="sxs-lookup"><span data-stu-id="cfb25-110">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cfb25-111">No se admite la recolección de elementos no utilizados simultánea en aplicaciones en las que se ejecuta el emulador WOW64 x86 en sistemas de 64 bits y que implementan la arquitectura Intel Itanium (denominada anteriormente IA-64).</span><span class="sxs-lookup"><span data-stu-id="cfb25-111">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="cfb25-112">Para obtener más información sobre el uso de WOW64 en sistemas Windows de 64 bits, vea [ejecutar aplicaciones de 32 bits](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="cfb25-112">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="cfb25-113">Determinar si se cargan los ensamblados como neutrales con respecto al dominio.</span><span class="sxs-lookup"><span data-stu-id="cfb25-113">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="cfb25-114">Obtener un puntero de interfaz a [ICorRuntimeHost](icorruntimehost-interface.md) que se puede utilizar para establecer opciones adicionales para configurar una instancia de CLR antes de que se inicie.</span><span class="sxs-lookup"><span data-stu-id="cfb25-114">Obtain an interface pointer to an [ICorRuntimeHost](icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb25-115">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfb25-115">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,
    [in]  LPCWSTR      pwszBuildFlavor,
    [in]  DWORD        startupFlags,
    [in]  REFCLSID     rclsid,
    [in]  REFIID       riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfb25-116">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfb25-116">Parameters</span></span>  

 `pwszVersion`  
 <span data-ttu-id="cfb25-117">[in] Cadena que describe la versión de CLR que se desea cargar.</span><span class="sxs-lookup"><span data-stu-id="cfb25-117">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="cfb25-118">Un número de versión en el .NET Framework consta de cuatro partes separadas por puntos: *Major. minor. Build. revision*.</span><span class="sxs-lookup"><span data-stu-id="cfb25-118">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="cfb25-119">La cadena que se pasó como `pwszVersion` debe comenzar con el carácter "v" seguido de las primeras tres partes del número de versión (por ejemplo, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="cfb25-119">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="cfb25-120">Algunas versiones de CLR se instalan con una instrucción de directiva que especifica la compatibilidad con versiones anteriores de CLR.</span><span class="sxs-lookup"><span data-stu-id="cfb25-120">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="cfb25-121">De forma predeterminada, el proceso intermedio ("shim") de inicio evalúa `pwszVersion` con las instrucciones de directiva y carga la versión más reciente del runtime compatible con la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="cfb25-121">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="cfb25-122">Un host puede hacer que el proceso intermedio ("shim") omita la evaluación de directivas y cargue exactamente la versión especificada en `pwszVersion`, pasando el valor `STARTUP_LOADER_SAFEMODE` para el parámetro `startupFlags`, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="cfb25-122">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="cfb25-123">Si el llamador especifica null como valor de `pwszVersion`, `CorBindToRuntimeEx` identifica el conjunto de runtime instalados cuyos números de versión son inferiores al del runtime de .NET Framework 4, y carga la versión más reciente del runtime desde dicho conjunto.</span><span class="sxs-lookup"><span data-stu-id="cfb25-123">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="cfb25-124">No cargará .NET Framework 4 ni versiones posteriores, y producirá un error si no hay ninguna versión anterior instalada.</span><span class="sxs-lookup"><span data-stu-id="cfb25-124">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="cfb25-125">Tenga en cuenta que pasar NULL impide al host controlar la versión del runtime que se carga.</span><span class="sxs-lookup"><span data-stu-id="cfb25-125">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="cfb25-126">Aunque este planteamiento puede ser apropiado en algunos escenarios, se recomienda encarecidamente que el host proponga cargar una versión específica.</span><span class="sxs-lookup"><span data-stu-id="cfb25-126">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="cfb25-127">[in] Cadena que especifica si se debe cargar la compilación de CLR para servidor o para estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cfb25-127">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="cfb25-128">Los valores válidos son `svr` y `wks`.</span><span class="sxs-lookup"><span data-stu-id="cfb25-128">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="cfb25-129">La compilación para servidor está optimizada para aprovechar las ventajas que aportan varios procesadores al realizar recolecciones de elementos no utilizados, mientras que la compilación para estación de trabajo está optimizada para aplicaciones cliente que se ejecutan en equipos con un solo procesador.</span><span class="sxs-lookup"><span data-stu-id="cfb25-129">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="cfb25-130">Si `pwszBuildFlavor` está establecido en null, se carga la compilación de la estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cfb25-130">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="cfb25-131">Cuando se ejecuta en un equipo de un solo procesador, siempre se carga la compilación de la estación de trabajo, incluso si `pwszBuildFlavor` se establece en `svr` .</span><span class="sxs-lookup"><span data-stu-id="cfb25-131">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="cfb25-132">Sin embargo, si `pwszBuildFlavor` se establece en `svr` y se especifica la recolección de elementos no utilizados simultánea (vea la descripción del `startupFlags` parámetro), se cargará la compilación del servidor.</span><span class="sxs-lookup"><span data-stu-id="cfb25-132">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="cfb25-133">de Combinación de valores de la enumeración [STARTUP_FLAGS](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="cfb25-133">[in] A combination of values of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="cfb25-134">Estos marcadores controlan la recolección de elementos no utilizados simultánea, el código neutral respecto al dominio y el comportamiento del parámetro `pwszVersion`.</span><span class="sxs-lookup"><span data-stu-id="cfb25-134">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="cfb25-135">Si no se establece ninguna marca, el valor predeterminado es un dominio único.</span><span class="sxs-lookup"><span data-stu-id="cfb25-135">The default is single domain if no flag is set.</span></span> <span data-ttu-id="cfb25-136">Valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="cfb25-136">The following values are valid:</span></span>  
  
- `STARTUP_CONCURRENT_GC`  
  
- `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
- `STARTUP_LOADER_SAFEMODE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_LOADER_SETPREFERENCE`  
  
- `STARTUP_SERVER_GC`  
  
- `STARTUP_HOARD_GC_VM`  
  
- `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
- `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 <span data-ttu-id="cfb25-137">Para obtener descripciones de estas marcas, vea la enumeración [STARTUP_FLAGS](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="cfb25-137">For descriptions of these flags, see the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="cfb25-138">de `CLSID` De la coclase que implementa la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="cfb25-138">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="cfb25-139">Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="cfb25-139">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="cfb25-140">[in] `IID` de la interfaz solicitada de `rclsid`.</span><span class="sxs-lookup"><span data-stu-id="cfb25-140">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="cfb25-141">Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="cfb25-141">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="cfb25-142">[out] Puntero de interfaz devuelto a `riid`.</span><span class="sxs-lookup"><span data-stu-id="cfb25-142">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfb25-143">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cfb25-143">Remarks</span></span>  

 <span data-ttu-id="cfb25-144">Si `pwszVersion` especifica una versión del runtime que no existe, `CorBindToRuntimeEx` devuelve un valor HRESULT de CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="cfb25-144">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="cfb25-145">Flujo y contexto de ejecución de la identidad de Windows</span><span class="sxs-lookup"><span data-stu-id="cfb25-145">Execution Context and Flow of Windows Identity</span></span>  

 <span data-ttu-id="cfb25-146">En la versión 1 de CLR, el objeto <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos, como nuevos subprocesos, grupos de subprocesos o devoluciones de llamada de temporizador.</span><span class="sxs-lookup"><span data-stu-id="cfb25-146">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="cfb25-147">En la versión 2.0 de CLR, el objeto <xref:System.Threading.ExecutionContext> ajusta cierta información sobre el subproceso en ejecución y hace que fluya por cualquier punto asincrónico, pero no por los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="cfb25-147">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="cfb25-148">De igual forma, el objeto <xref:System.Security.Principal.WindowsIdentity> también fluye por cualquier punto asincrónico.</span><span class="sxs-lookup"><span data-stu-id="cfb25-148">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="cfb25-149">Por consiguiente, también fluye la suplantación actual en el subproceso, si la hubiera.</span><span class="sxs-lookup"><span data-stu-id="cfb25-149">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="cfb25-150">El flujo puede modificarse de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="cfb25-150">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="cfb25-151">Si se modifica la configuración de <xref:System.Threading.ExecutionContext> para suprimir el flujo por subproceso (vea los métodos <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A> y <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>).</span><span class="sxs-lookup"><span data-stu-id="cfb25-151">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="cfb25-152">Si se cambia el modo predeterminado del proceso al modo de compatibilidad de la versión 1, donde el objeto <xref:System.Security.Principal.WindowsIdentity> no fluye por ningún punto asincrónico, independientemente de los valores de <xref:System.Threading.ExecutionContext> en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="cfb25-152">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="cfb25-153">La manera de cambiar el modo predeterminado depende de si se usa un archivo ejecutable administrado o una interfaz de hospedaje no administrada para cargar CLR:</span><span class="sxs-lookup"><span data-stu-id="cfb25-153">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="cfb25-154">Para los ejecutables administrados, debe establecer el `enabled` atributo del [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) elemento en `true` .</span><span class="sxs-lookup"><span data-stu-id="cfb25-154">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="cfb25-155">Para las interfaces de hospedaje no administradas, se establece la marca `STARTUP_LEGACY_IMPERSONATION` en el parámetro `startupFlags` al llamar a la función `CorBindToRuntimeEx`.</span><span class="sxs-lookup"><span data-stu-id="cfb25-155">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="cfb25-156">El modo de compatibilidad de la versión 1 se aplica a todo el proceso y a todos los dominios de aplicación del proceso.</span><span class="sxs-lookup"><span data-stu-id="cfb25-156">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfb25-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfb25-157">Requirements</span></span>  

 <span data-ttu-id="cfb25-158">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfb25-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfb25-159">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cfb25-159">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cfb25-160">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cfb25-160">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfb25-161">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfb25-161">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb25-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfb25-162">See also</span></span>

- [<span data-ttu-id="cfb25-163">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="cfb25-163">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="cfb25-164">CorBindToRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="cfb25-164">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="cfb25-165">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="cfb25-165">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="cfb25-166">CorBindToRuntimeHost (Función)</span><span class="sxs-lookup"><span data-stu-id="cfb25-166">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="cfb25-167">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cfb25-167">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="cfb25-168">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="cfb25-168">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
