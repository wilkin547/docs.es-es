---
title: "ICLRErrorReportingManager::BeginCustomDump (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.BeginCustomDump
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d09afd9fe0a2905c79ffb2d50b342041865b593b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="28548-102">ICLRErrorReportingManager::BeginCustomDump (Método)</span><span class="sxs-lookup"><span data-stu-id="28548-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="28548-103">Especifica la configuración de los volcados del montón personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="28548-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28548-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28548-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28548-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28548-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="28548-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) valor que indica el tipo de volcado de memoria del montón en el que se va a crear el volcado del montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="28548-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="28548-107">[in] La longitud de la `items` matriz.</span><span class="sxs-lookup"><span data-stu-id="28548-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="28548-108">Si `dwFlavor` no es DUMP_FLAVOR_Mini, `dwNumItems` debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="28548-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="28548-109">[in] Una matriz de [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instancias, especificar los elementos que se va a agregar al minivolcado.</span><span class="sxs-lookup"><span data-stu-id="28548-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="28548-110">Si `dwFlavor` no es DUMP_FLAVOR_Mini, `items` debe ser null.</span><span class="sxs-lookup"><span data-stu-id="28548-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="28548-111">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="28548-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28548-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="28548-112">Return Value</span></span>  
  
|<span data-ttu-id="28548-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28548-113">HRESULT</span></span>|<span data-ttu-id="28548-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="28548-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28548-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="28548-115">S_OK</span></span>|<span data-ttu-id="28548-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="28548-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="28548-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="28548-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="28548-118">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="28548-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="28548-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="28548-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="28548-120">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="28548-120">The call timed out.</span></span>|  
|<span data-ttu-id="28548-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="28548-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="28548-122">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="28548-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="28548-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="28548-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="28548-124">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="28548-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="28548-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28548-125">E_FAIL</span></span>|<span data-ttu-id="28548-126">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="28548-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="28548-127">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="28548-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="28548-128">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="28548-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28548-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28548-129">Remarks</span></span>  
 <span data-ttu-id="28548-130">El `BeginCustomDump` método establece la configuración de volcado de memoria de montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="28548-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="28548-131">El [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) método borra la configuración de volcado de memoria de montón personalizado y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="28548-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="28548-132">Debe llamarse una vez completado el volcado del montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="28548-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="28548-133">Error al llamar a `EndCustomDump` provoca la pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="28548-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28548-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28548-134">Requirements</span></span>  
 <span data-ttu-id="28548-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28548-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28548-136">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28548-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28548-137">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28548-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28548-138">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28548-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28548-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="28548-139">See Also</span></span>  
 [<span data-ttu-id="28548-140">CustomDumpItem (estructura)</span><span class="sxs-lookup"><span data-stu-id="28548-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [<span data-ttu-id="28548-141">ECustomDumpFlavor (enumeración)</span><span class="sxs-lookup"><span data-stu-id="28548-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [<span data-ttu-id="28548-142">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28548-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
