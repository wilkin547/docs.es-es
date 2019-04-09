---
title: ICLRErrorReportingManager::BeginCustomDump (Método)
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cb6cd8d31e01ea2f1749a6cb4d17173679f0c06
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104122"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="d646d-102">ICLRErrorReportingManager::BeginCustomDump (Método)</span><span class="sxs-lookup"><span data-stu-id="d646d-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="d646d-103">Especifica la configuración de los volcados de montón personalizado para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="d646d-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d646d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d646d-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d646d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d646d-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="d646d-106">[in] Un [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) valor que indica el tipo de volcado del montón al que se va a compilar el volcado del montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="d646d-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="d646d-107">[in] La longitud de la `items` matriz.</span><span class="sxs-lookup"><span data-stu-id="d646d-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="d646d-108">Si `dwFlavor` no es DUMP_FLAVOR_Mini, `dwNumItems` debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="d646d-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="d646d-109">[in] Una matriz de [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instancias, especificar los elementos que se van a agregar en el minivolcado.</span><span class="sxs-lookup"><span data-stu-id="d646d-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="d646d-110">Si `dwFlavor` no es DUMP_FLAVOR_Mini, `items` debe ser null.</span><span class="sxs-lookup"><span data-stu-id="d646d-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="d646d-111">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="d646d-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d646d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d646d-112">Return Value</span></span>  
  
|<span data-ttu-id="d646d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d646d-113">HRESULT</span></span>|<span data-ttu-id="d646d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d646d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d646d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d646d-115">S_OK</span></span>|<span data-ttu-id="d646d-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d646d-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="d646d-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d646d-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d646d-118">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d646d-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d646d-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d646d-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d646d-120">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d646d-120">The call timed out.</span></span>|  
|<span data-ttu-id="d646d-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d646d-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d646d-122">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d646d-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d646d-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d646d-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d646d-124">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="d646d-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d646d-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d646d-125">E_FAIL</span></span>|<span data-ttu-id="d646d-126">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="d646d-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d646d-127">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d646d-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d646d-128">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d646d-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d646d-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d646d-129">Remarks</span></span>  
 <span data-ttu-id="d646d-130">El `BeginCustomDump` método establece la configuración de volcado de memoria del montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="d646d-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="d646d-131">El [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) método borra la configuración de volcado del montón personalizado y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="d646d-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="d646d-132">Debe llamarse una vez completado el volcado del montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="d646d-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d646d-133">Error al llamar a `EndCustomDump` provoca la pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="d646d-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d646d-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d646d-134">Requirements</span></span>  
 <span data-ttu-id="d646d-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d646d-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d646d-136">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d646d-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d646d-137">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d646d-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d646d-138">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d646d-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d646d-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="d646d-139">See also</span></span>

- [<span data-ttu-id="d646d-140">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="d646d-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="d646d-141">ECustomDumpFlavor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d646d-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="d646d-142">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d646d-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
