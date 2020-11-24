---
title: CorBindToRuntimeHost (Función)
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
ms.openlocfilehash: 7ba35823ccb670ad0201d1950687dc83cc9ba64a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673753"
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="01098-102">CorBindToRuntimeHost (Función)</span><span class="sxs-lookup"><span data-stu-id="01098-102">CorBindToRuntimeHost Function</span></span>

<span data-ttu-id="01098-103">Permite a los hosts cargar una versión determinada de Common Language Runtime (CLR) en un proceso.</span><span class="sxs-lookup"><span data-stu-id="01098-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="01098-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="01098-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01098-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01098-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,
    [in] LPCWSTR       pwszBuildFlavor,
    [in] LPCWSTR       pwszHostConfigFile,
    [in] VOID*         pReserved,
    [in] DWORD         startupFlags,
    [in] REFCLSID      rclsid,
    [in] REFIID        riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01098-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01098-106">Parameters</span></span>  

 `pwszVersion`  
 <span data-ttu-id="01098-107">[in] Cadena que describe la versión de CLR que se desea cargar.</span><span class="sxs-lookup"><span data-stu-id="01098-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="01098-108">Un número de versión en el .NET Framework consta de cuatro partes separadas por puntos: *Major. minor. Build. revision*.</span><span class="sxs-lookup"><span data-stu-id="01098-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="01098-109">La cadena que se pasó como `pwszVersion` debe comenzar con el carácter "v" seguido de las primeras tres partes del número de versión (por ejemplo, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="01098-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="01098-110">Algunas versiones de CLR se instalan con una instrucción de directiva que especifica la compatibilidad con versiones anteriores de CLR.</span><span class="sxs-lookup"><span data-stu-id="01098-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="01098-111">De forma predeterminada, el proceso intermedio ("shim") de inicio evalúa `pwszVersion` con las instrucciones de directiva y carga la versión más reciente del runtime compatible con la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="01098-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="01098-112">Un host puede hacer que el proceso intermedio ("shim") omita la evaluación de directivas y cargue exactamente la versión especificada en `pwszVersion`, pasando el valor STARTUP_LOADER_SAFEMODE para el parámetro `startupFlags`.</span><span class="sxs-lookup"><span data-stu-id="01098-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="01098-113">Si `pwszVersion` es `null,` el método no carga ninguna versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="01098-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="01098-114">En su lugar, devuelve CLR_E_SHIM_RUNTIMELOAD, que indica que no se cargó el runtime.</span><span class="sxs-lookup"><span data-stu-id="01098-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="01098-115">[in] Cadena que especifica si se debe cargar la compilación de CLR para servidor o para estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="01098-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="01098-116">Los valores válidos son `svr` y `wks`.</span><span class="sxs-lookup"><span data-stu-id="01098-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="01098-117">La compilación para servidor está optimizada para aprovechar las ventajas que aportan varios procesadores al realizar recolecciones de elementos no utilizados, mientras que la compilación para estación de trabajo está optimizada para aplicaciones cliente que se ejecutan en equipos con un solo procesador.</span><span class="sxs-lookup"><span data-stu-id="01098-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="01098-118">Si `pwszBuildFlavor` está establecido en null, se carga la compilación de la estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="01098-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="01098-119">Cuando se ejecuta en un equipo de un solo procesador, siempre se carga la compilación de la estación de trabajo, incluso si `pwszBuildFlavor` se establece en `svr` .</span><span class="sxs-lookup"><span data-stu-id="01098-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="01098-120">Sin embargo, si `pwszBuildFlavor` se establece en `svr` y se especifica la recolección de elementos no utilizados simultánea (vea la descripción del `startupFlags` parámetro), se cargará la compilación del servidor.</span><span class="sxs-lookup"><span data-stu-id="01098-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01098-121">No se admite la recolección de elementos no utilizados simultánea en aplicaciones en las que se ejecuta el emulador WOW64 x86 en sistemas de 64 bits y que implementan la arquitectura Intel Itanium (denominada anteriormente IA-64).</span><span class="sxs-lookup"><span data-stu-id="01098-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="01098-122">Para obtener más información sobre el uso de WOW64 en sistemas Windows de 64 bits, vea [ejecutar aplicaciones de 32 bits](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="01098-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="01098-123">[in] Nombre de un archivo de configuración de host que especifica la versión de CLR que se debe cargar.</span><span class="sxs-lookup"><span data-stu-id="01098-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="01098-124">Si el nombre de archivo no incluye una ruta de acceso completa, se supone que este se encuentra en el mismo directorio que el ejecutable que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="01098-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="01098-125">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="01098-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="01098-126">[in] Conjunto de marcas que controla la recolección de elementos no utilizados simultánea, el código neutral respecto al dominio y el comportamiento del parámetro `pwszVersion`.</span><span class="sxs-lookup"><span data-stu-id="01098-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="01098-127">Si no se establece ninguna marca, el valor predeterminado es un dominio único.</span><span class="sxs-lookup"><span data-stu-id="01098-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="01098-128">Para obtener una lista de valores admitidos, vea la [enumeración STARTUP_FLAGS](startup-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="01098-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="01098-129">de `CLSID` De la coclase que implementa la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="01098-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="01098-130">Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="01098-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="01098-131">[in] El `IID` de la interfaz solicitada.</span><span class="sxs-lookup"><span data-stu-id="01098-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="01098-132">Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="01098-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="01098-133">[out] Puntero de interfaz a la versión del runtime que se cargó.</span><span class="sxs-lookup"><span data-stu-id="01098-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01098-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01098-134">Requirements</span></span>  

 <span data-ttu-id="01098-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01098-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01098-136">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="01098-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="01098-137">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01098-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01098-138">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01098-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01098-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01098-139">See also</span></span>

- [<span data-ttu-id="01098-140">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="01098-140">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="01098-141">CorBindToRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="01098-141">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="01098-142">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="01098-142">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="01098-143">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="01098-143">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="01098-144">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="01098-144">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="01098-145">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="01098-145">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
