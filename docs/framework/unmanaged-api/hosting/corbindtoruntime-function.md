---
description: 'Más información acerca de: CorBindToRuntime (función)'
title: CorBindToRuntime (Función)
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
ms.openlocfilehash: 727abdccd692a431960d293404025cf9ccc1d7ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790092"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="e0cfd-103">CorBindToRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="e0cfd-103">CorBindToRuntime Function</span></span>

<span data-ttu-id="e0cfd-104">Permite a los hosts no administrados cargar Common Language Runtime (CLR) en un proceso.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-104">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="e0cfd-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0cfd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0cfd-106">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0cfd-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0cfd-107">Parameters</span></span>  

 `pwszVersion`  
 <span data-ttu-id="e0cfd-108">[in] Cadena que describe la versión de CLR que se desea cargar.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-108">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="e0cfd-109">Un número de versión en el .NET Framework consta de cuatro partes separadas por puntos: *Major. minor. Build. revision*.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-109">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="e0cfd-110">La cadena que se pasó como `pwszVersion` debe comenzar con el carácter "v" seguido de las primeras tres partes del número de versión (por ejemplo, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="e0cfd-110">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="e0cfd-111">Algunas versiones de CLR se instalan con una instrucción de directiva que especifica la compatibilidad con versiones anteriores de CLR.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-111">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="e0cfd-112">De forma predeterminada, el proceso intermedio ("shim") de inicio evalúa `pwszVersion` con las instrucciones de directiva y carga la versión más reciente del runtime compatible con la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-112">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="e0cfd-113">Un host puede hacer que el proceso intermedio ("shim") omita la evaluación de directivas y cargue exactamente la versión especificada en `pwszVersion`, pasando el valor `STARTUP_LOADER_SAFEMODE` para el parámetro `flags`, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-113">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="e0cfd-114">Si el autor de la llamada especifica null para `pwszVersion` , se cargará la versión más reciente del Runtime.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-114">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="e0cfd-115">Pasar null proporciona al host ningún control sobre qué versión del Runtime se carga.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-115">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="e0cfd-116">Aunque este planteamiento puede ser apropiado en algunos escenarios, se recomienda encarecidamente que el host proponga cargar una versión específica.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-116">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="e0cfd-117">[in] Cadena que especifica si se debe cargar la compilación de CLR para servidor o para estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-117">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="e0cfd-118">Los valores válidos son `svr` y `wks`.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-118">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="e0cfd-119">La compilación para servidor está optimizada para aprovechar las ventajas que aportan varios procesadores al realizar recolecciones de elementos no utilizados, mientras que la compilación para estación de trabajo está optimizada para aplicaciones cliente que se ejecutan en equipos con un solo procesador.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-119">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="e0cfd-120">Si `pwszBuildFlavor` está establecido en null, se carga la compilación de la estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-120">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="e0cfd-121">Cuando se ejecuta en un equipo de un solo procesador, siempre se carga la compilación de la estación de trabajo, incluso si `pwszBuildFlavor` se establece en `svr` .</span><span class="sxs-lookup"><span data-stu-id="e0cfd-121">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="e0cfd-122">Sin embargo, si `pwszBuildFlavor` se establece en `svr` y se especifica la recolección de elementos no utilizados simultánea (vea la descripción del `flags` parámetro), se cargará la compilación del servidor.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-122">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="e0cfd-123">de `CLSID` De la coclase que implementa la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e0cfd-123">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="e0cfd-124">Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-124">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="e0cfd-125">[in] `IID` de la interfaz solicitada de `rclsid`.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-125">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="e0cfd-126">Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-126">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e0cfd-127">[out] Puntero de interfaz devuelto a `riid`.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-127">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0cfd-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e0cfd-128">Remarks</span></span>  

 <span data-ttu-id="e0cfd-129">Si `pwszVersion` especifica una versión del runtime que no existe, `CorBindToRuntimeEx` devuelve un valor HRESULT de CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-129">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="e0cfd-130">Flujo y contexto de ejecución de la identidad de Windows</span><span class="sxs-lookup"><span data-stu-id="e0cfd-130">Execution Context and Flow of Windows Identity</span></span>  

 <span data-ttu-id="e0cfd-131">En la versión 1 de CLR, el objeto <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos, como nuevos subprocesos, grupos de subprocesos o devoluciones de llamada de temporizador.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-131">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="e0cfd-132">En la versión 2.0 de CLR, el objeto <xref:System.Threading.ExecutionContext> ajusta cierta información sobre el subproceso en ejecución y hace que fluya por cualquier punto asincrónico, pero no por los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-132">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="e0cfd-133">De igual forma, el objeto <xref:System.Security.Principal.WindowsIdentity> también fluye por cualquier punto asincrónico.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-133">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="e0cfd-134">Por consiguiente, también fluye la suplantación actual en el subproceso, si la hubiera.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-134">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="e0cfd-135">El flujo puede modificarse de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="e0cfd-135">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="e0cfd-136">Si se modifica la configuración de <xref:System.Threading.ExecutionContext> para suprimir el flujo por subproceso (vea los métodos <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A> y <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>).</span><span class="sxs-lookup"><span data-stu-id="e0cfd-136">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="e0cfd-137">Si se cambia el modo predeterminado del proceso al modo de compatibilidad de la versión 1, donde el objeto <xref:System.Security.Principal.WindowsIdentity> no fluye por ningún punto asincrónico, independientemente de los valores de <xref:System.Threading.ExecutionContext> en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-137">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="e0cfd-138">La manera de cambiar el modo predeterminado depende de si se usa un archivo ejecutable administrado o una interfaz de hospedaje no administrada para cargar CLR:</span><span class="sxs-lookup"><span data-stu-id="e0cfd-138">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="e0cfd-139">Para los ejecutables administrados, debe establecer el `enabled` atributo del [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) elemento en `true` .</span><span class="sxs-lookup"><span data-stu-id="e0cfd-139">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="e0cfd-140">Para las interfaces de hospedaje no administradas, se establece la marca `STARTUP_LEGACY_IMPERSONATION` en el parámetro `flags` al llamar a la función `CorBindToRuntimeEx`.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-140">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="e0cfd-141">El modo de compatibilidad de la versión 1 se aplica a todo el proceso y a todos los dominios de aplicación del proceso.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-141">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0cfd-142">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e0cfd-142">Remarks</span></span>  

 <span data-ttu-id="e0cfd-143">[CorBindToRuntimeEx](corbindtoruntimeex-function.md) y `CorBindToRuntime` realizan la misma operación, pero la `CorBindToRuntimeEx` función permite establecer marcas para especificar el comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="e0cfd-143">[CorBindToRuntimeEx](corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0cfd-144">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0cfd-144">Requirements</span></span>  

 <span data-ttu-id="e0cfd-145">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0cfd-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0cfd-146">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e0cfd-146">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0cfd-147">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0cfd-147">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0cfd-148">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0cfd-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0cfd-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0cfd-149">See also</span></span>

- [<span data-ttu-id="e0cfd-150">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="e0cfd-150">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="e0cfd-151">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="e0cfd-151">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="e0cfd-152">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="e0cfd-152">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="e0cfd-153">CorBindToRuntimeHost (Función)</span><span class="sxs-lookup"><span data-stu-id="e0cfd-153">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="e0cfd-154">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0cfd-154">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="e0cfd-155">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="e0cfd-155">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
