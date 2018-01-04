---
title: ICLRMetaHost (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost
helpviewer_keywords: ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type: apiref
caps.latest.revision: "28"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a12635e14b694b361e2877041588d7d9f08a4102
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="51d9b-102">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51d9b-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="51d9b-103">Proporciona métodos que devuelven una versión concreta de common language runtime (CLR) en función de su número de versión, enumerar todos los CLR instalados, lista de todos los runtimes que se cargan en un determinado proceso, detección la versión CLR utilizada para compilar un ensamblado, sale de un proceso con un apagado de runtime limpio y enlace de API heredado de consulta.</span><span class="sxs-lookup"><span data-stu-id="51d9b-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51d9b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="51d9b-104">Methods</span></span>  
  
|<span data-ttu-id="51d9b-105">Método</span><span class="sxs-lookup"><span data-stu-id="51d9b-105">Method</span></span>|<span data-ttu-id="51d9b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="51d9b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51d9b-107">EnumerateInstalledRuntimes (método)</span><span class="sxs-lookup"><span data-stu-id="51d9b-107">EnumerateInstalledRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="51d9b-108">Devuelve una enumeración que contiene un válido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) puntero de interfaz para cada versión CLR que se instala en un equipo.</span><span class="sxs-lookup"><span data-stu-id="51d9b-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="51d9b-109">EnumerateLoadedRuntimes (método)</span><span class="sxs-lookup"><span data-stu-id="51d9b-109">EnumerateLoadedRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="51d9b-110">Devuelve una enumeración que contiene un válido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) puntero de interfaz para cada CLR que se carga en un proceso determinado.</span><span class="sxs-lookup"><span data-stu-id="51d9b-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="51d9b-111">Este método reemplaza a [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="51d9b-111">This method supersedes [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="51d9b-112">ExitProcess (método)</span><span class="sxs-lookup"><span data-stu-id="51d9b-112">ExitProcess Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|<span data-ttu-id="51d9b-113">Intenta cerrar todos los runtime cargados correctamente y, a continuación, finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="51d9b-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="51d9b-114">Reemplaza el [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="51d9b-114">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="51d9b-115">GetRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="51d9b-115">GetRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|<span data-ttu-id="51d9b-116">Obtiene el [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que corresponde a una versión determinada de CLR.</span><span class="sxs-lookup"><span data-stu-id="51d9b-116">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="51d9b-117">Este método reemplaza a la [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) función que se usa con la [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) marca.</span><span class="sxs-lookup"><span data-stu-id="51d9b-117">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="51d9b-118">GetVersionFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="51d9b-118">GetVersionFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="51d9b-119">Obtiene .NET Framework versión de compilación original del ensamblado (que se almacena en los metadatos), dada su ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="51d9b-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="51d9b-120">Este método reemplaza a [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span><span class="sxs-lookup"><span data-stu-id="51d9b-120">This method supersedes [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="51d9b-121">QueryLegacyV2RuntimeBinding (método)</span><span class="sxs-lookup"><span data-stu-id="51d9b-121">QueryLegacyV2RuntimeBinding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="51d9b-122">Devuelve una interfaz que representa un tiempo de ejecución a la que Directiva de activación heredada se ha enlazado, por ejemplo mediante el uso de la `useLegacyV2RuntimeActivationPolicy` del atributo en el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) entrada del archivo de configuración mediante el uso directo de la API de activación heredadas o llamando a la [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="51d9b-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="51d9b-123">RequestRuntimeLoadedNotification (método)</span><span class="sxs-lookup"><span data-stu-id="51d9b-123">RequestRuntimeLoadedNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="51d9b-124">Garantiza una devolución de llamada al puntero de función especificado cuando una versión CLR se carga por primera vez, pero aún no se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="51d9b-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="51d9b-125">Este método reemplaza a [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="51d9b-125">This method supersedes [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51d9b-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51d9b-126">Remarks</span></span>  
 <span data-ttu-id="51d9b-127">La única manera de obtener una instancia de esta interfaz es mediante una llamada a la [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funcione como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="51d9b-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as follows:</span></span>  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="51d9b-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51d9b-128">Requirements</span></span>  
 <span data-ttu-id="51d9b-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51d9b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51d9b-130">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="51d9b-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="51d9b-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51d9b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51d9b-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51d9b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51d9b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="51d9b-133">See Also</span></span>  
 [<span data-ttu-id="51d9b-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="51d9b-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="51d9b-135">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="51d9b-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
