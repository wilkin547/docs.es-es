---
title: ICLRMetaHost (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: 391adc6f9fe55ad7ca527ea416956ab013a27b15
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703722"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="a5be9-102">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5be9-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="a5be9-103">Proporciona métodos que devuelven una versión específica de la Common Language Runtime (CLR) en función de su número de versión, enumeran todos los CLR instalados, enumeran todos los Runtimes que se cargan en un proceso especificado, detectan la versión de CLR usada para compilar un ensamblado, salen un proceso con un apagado limpio del tiempo de ejecución y consulta el enlace de API heredado</span><span class="sxs-lookup"><span data-stu-id="a5be9-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5be9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a5be9-104">Methods</span></span>  
  
|<span data-ttu-id="a5be9-105">Método</span><span class="sxs-lookup"><span data-stu-id="a5be9-105">Method</span></span>|<span data-ttu-id="a5be9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5be9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5be9-107">Método EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="a5be9-107">EnumerateInstalledRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="a5be9-108">Devuelve una enumeración que contiene un puntero de interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) válido para cada versión de CLR que está instalada en un equipo.</span><span class="sxs-lookup"><span data-stu-id="a5be9-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="a5be9-109">Método EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="a5be9-109">EnumerateLoadedRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="a5be9-110">Devuelve una enumeración que contiene un puntero de interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) válido para cada CLR que se carga en un proceso determinado.</span><span class="sxs-lookup"><span data-stu-id="a5be9-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="a5be9-111">Este método reemplaza a [GetVersionFromProcess (](getversionfromprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="a5be9-111">This method supersedes [GetVersionFromProcess](getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="a5be9-112">ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="a5be9-112">ExitProcess Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|<span data-ttu-id="a5be9-113">Intenta cerrar todos los tiempos de ejecución cargados correctamente y, a continuación, finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="a5be9-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="a5be9-114">Reemplaza la función [CorExitProcess (](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="a5be9-114">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="a5be9-115">Método GetRuntime</span><span class="sxs-lookup"><span data-stu-id="a5be9-115">GetRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|<span data-ttu-id="a5be9-116">Obtiene la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) que corresponde a una versión de CLR determinada.</span><span class="sxs-lookup"><span data-stu-id="a5be9-116">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="a5be9-117">Este método reemplaza a la función [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) utilizada con la marca [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="a5be9-117">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="a5be9-118">Método GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="a5be9-118">GetVersionFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="a5be9-119">Obtiene la versión de compilación original .NET Framework del ensamblado (almacenada en los metadatos), dada su ruta de acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="a5be9-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="a5be9-120">Este método reemplaza a [GetFileVersion (](getfileversion-function.md).</span><span class="sxs-lookup"><span data-stu-id="a5be9-120">This method supersedes [GetFileVersion](getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="a5be9-121">Método QueryLegacyV2RuntimeBinding</span><span class="sxs-lookup"><span data-stu-id="a5be9-121">QueryLegacyV2RuntimeBinding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="a5be9-122">Devuelve una interfaz que representa un tiempo de ejecución en el que se ha enlazado la Directiva de activación heredada, por ejemplo, mediante el uso del `useLegacyV2RuntimeActivationPolicy` atributo en la entrada del archivo de configuración del [ \< elemento> de inicio](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) , mediante el uso directo de las API de activación heredadas o llamando al método [ICLRRuntimeInfo:: BindAsLegacyV2Runtime (](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a5be9-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="a5be9-123">Método RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="a5be9-123">RequestRuntimeLoadedNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="a5be9-124">Garantiza una devolución de llamada al puntero de función especificado cuando se carga por primera vez una versión de CLR, pero aún no se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="a5be9-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="a5be9-125">Este método reemplaza a [LockClrVersion](lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="a5be9-125">This method supersedes [LockClrVersion](lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5be9-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a5be9-126">Remarks</span></span>  
 <span data-ttu-id="a5be9-127">La única forma de obtener una instancia de esta interfaz es mediante una llamada a la función [CLRCreateInstance](clrcreateinstance-function.md) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a5be9-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as follows:</span></span>  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a5be9-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5be9-128">Requirements</span></span>  
 <span data-ttu-id="a5be9-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5be9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5be9-130">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="a5be9-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a5be9-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a5be9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5be9-132">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5be9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5be9-133">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a5be9-133">See also</span></span>

- [<span data-ttu-id="a5be9-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a5be9-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a5be9-135">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="a5be9-135">Hosting</span></span>](index.md)
