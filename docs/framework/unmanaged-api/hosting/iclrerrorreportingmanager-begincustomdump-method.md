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
ms.openlocfilehash: 4c83ffaf920abe005ba987e0a744e13aa0d3c016
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615675"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="1add3-102">ICLRErrorReportingManager::BeginCustomDump (Método)</span><span class="sxs-lookup"><span data-stu-id="1add3-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="1add3-103">Especifica la configuración de volcados de montón personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="1add3-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1add3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1add3-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1add3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1add3-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="1add3-106">de Un valor [ecustomdumpflavor (](ecustomdumpflavor-enumeration.md) que indica el tipo de volcado del montón en el que se va a generar el volcado del montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="1add3-106">[in] A [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="1add3-107">de Longitud de la `items` matriz.</span><span class="sxs-lookup"><span data-stu-id="1add3-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="1add3-108">Si `dwFlavor` no es DUMP_FLAVOR_Mini, `dwNumItems` debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="1add3-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="1add3-109">de Una matriz de instancias de [customdumpitem (](customdumpitem-structure.md) , que especifica los elementos que se van a agregar al minivolcado.</span><span class="sxs-lookup"><span data-stu-id="1add3-109">[in] An array of [CustomDumpItem](customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="1add3-110">Si `dwFlavor` no es DUMP_FLAVOR_Mini, `items` debe ser null.</span><span class="sxs-lookup"><span data-stu-id="1add3-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="1add3-111">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="1add3-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1add3-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1add3-112">Return Value</span></span>  
  
|<span data-ttu-id="1add3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1add3-113">HRESULT</span></span>|<span data-ttu-id="1add3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1add3-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1add3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="1add3-115">S_OK</span></span>|<span data-ttu-id="1add3-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1add3-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="1add3-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1add3-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1add3-118">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1add3-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1add3-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1add3-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1add3-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1add3-120">The call timed out.</span></span>|  
|<span data-ttu-id="1add3-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1add3-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1add3-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1add3-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1add3-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1add3-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1add3-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="1add3-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1add3-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1add3-125">E_FAIL</span></span>|<span data-ttu-id="1add3-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1add3-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1add3-127">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1add3-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1add3-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1add3-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1add3-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1add3-129">Remarks</span></span>  
 <span data-ttu-id="1add3-130">El `BeginCustomDump` método establece la configuración personalizada del volcado del montón.</span><span class="sxs-lookup"><span data-stu-id="1add3-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="1add3-131">El método [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) borra la configuración de volcado del montón personalizado y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="1add3-131">The [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="1add3-132">Se debe llamar después de que se complete el volcado del montón personalizado.</span><span class="sxs-lookup"><span data-stu-id="1add3-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1add3-133">Si no se llama a `EndCustomDump` , se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="1add3-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1add3-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1add3-134">Requirements</span></span>  
 <span data-ttu-id="1add3-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1add3-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1add3-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1add3-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1add3-137">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1add3-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1add3-138">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1add3-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1add3-139">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1add3-139">See also</span></span>

- [<span data-ttu-id="1add3-140">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="1add3-140">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="1add3-141">ECustomDumpFlavor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1add3-141">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="1add3-142">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1add3-142">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
