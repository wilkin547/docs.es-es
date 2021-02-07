---
description: 'Más información acerca de: ICLRErrorReportingManager:: BeginCustomDump (método)'
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
ms.openlocfilehash: 3f8498068d50ffc6ea00cf4f08f969c92f010d6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689487"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="c1ad9-103">ICLRErrorReportingManager::BeginCustomDump (Método)</span><span class="sxs-lookup"><span data-stu-id="c1ad9-103">ICLRErrorReportingManager::BeginCustomDump Method</span></span>

<span data-ttu-id="c1ad9-104">Especifica la configuración de volcados de montón personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-104">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ad9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1ad9-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1ad9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1ad9-106">Parameters</span></span>  

 `dwFlavor`  
 <span data-ttu-id="c1ad9-107">de Un valor [ecustomdumpflavor (](ecustomdumpflavor-enumeration.md) que indica el tipo de volcado del montón en el que se va a generar el volcado del montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-107">[in] A [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="c1ad9-108">de Longitud de la `items` matriz.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-108">[in] The length of the `items` array.</span></span> <span data-ttu-id="c1ad9-109">Si `dwFlavor` no es DUMP_FLAVOR_Mini, `dwNumItems` debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-109">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="c1ad9-110">de Una matriz de instancias de [customdumpitem (](customdumpitem-structure.md) , que especifica los elementos que se van a agregar al minivolcado.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-110">[in] An array of [CustomDumpItem](customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="c1ad9-111">Si `dwFlavor` no es DUMP_FLAVOR_Mini, `items` debe ser null.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-111">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="c1ad9-112">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-112">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1ad9-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c1ad9-113">Return Value</span></span>  
  
|<span data-ttu-id="c1ad9-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1ad9-114">HRESULT</span></span>|<span data-ttu-id="c1ad9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1ad9-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1ad9-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1ad9-116">S_OK</span></span>|<span data-ttu-id="c1ad9-117">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-117">The method returned successfully.</span></span>|  
|<span data-ttu-id="c1ad9-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c1ad9-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c1ad9-119">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c1ad9-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1ad9-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c1ad9-121">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-121">The call timed out.</span></span>|  
|<span data-ttu-id="c1ad9-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c1ad9-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c1ad9-123">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c1ad9-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c1ad9-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c1ad9-125">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c1ad9-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c1ad9-126">E_FAIL</span></span>|<span data-ttu-id="c1ad9-127">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c1ad9-128">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c1ad9-129">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1ad9-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c1ad9-130">Remarks</span></span>  

 <span data-ttu-id="c1ad9-131">El `BeginCustomDump` método establece la configuración personalizada del volcado del montón.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-131">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="c1ad9-132">El método [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) borra la configuración de volcado del montón personalizado y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-132">The [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="c1ad9-133">Se debe llamar después de que se complete el volcado del montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-133">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c1ad9-134">Si no se llama a `EndCustomDump` , se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="c1ad9-134">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ad9-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1ad9-135">Requirements</span></span>  

 <span data-ttu-id="c1ad9-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ad9-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ad9-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c1ad9-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1ad9-138">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1ad9-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1ad9-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ad9-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ad9-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1ad9-140">See also</span></span>

- [<span data-ttu-id="c1ad9-141">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="c1ad9-141">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="c1ad9-142">ECustomDumpFlavor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c1ad9-142">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="c1ad9-143">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1ad9-143">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
