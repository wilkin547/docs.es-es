---
title: ICLRErrorReportingManager::EndCustomDump (Método)
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a262ab26c9bbb93e42a11217fbeea6b3c55c7eb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966260"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="59b1f-102">ICLRErrorReportingManager::EndCustomDump (Método)</span><span class="sxs-lookup"><span data-stu-id="59b1f-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="59b1f-103">Quita la configuración de volcado de la pila personalizada que se especificó en una llamada anterior al método [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="59b1f-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b1f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59b1f-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="59b1f-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="59b1f-105">Return Value</span></span>  
  
|<span data-ttu-id="59b1f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59b1f-106">HRESULT</span></span>|<span data-ttu-id="59b1f-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59b1f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59b1f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="59b1f-108">S_OK</span></span>|<span data-ttu-id="59b1f-109">`EndCustomDump`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="59b1f-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="59b1f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="59b1f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="59b1f-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="59b1f-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="59b1f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="59b1f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="59b1f-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59b1f-113">The call timed out.</span></span>|  
|<span data-ttu-id="59b1f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="59b1f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="59b1f-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="59b1f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="59b1f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="59b1f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="59b1f-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="59b1f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="59b1f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="59b1f-118">E_FAIL</span></span>|<span data-ttu-id="59b1f-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="59b1f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="59b1f-120">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="59b1f-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="59b1f-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="59b1f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59b1f-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59b1f-122">Remarks</span></span>  
 <span data-ttu-id="59b1f-123">El `EndCustomDump` método borra la configuración de volcado de pila personalizada establecida por una llamada anterior `BeginCustomDump` al método y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="59b1f-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="59b1f-124">Se debe llamar después de completar el volcado de la pila personalizado.</span><span class="sxs-lookup"><span data-stu-id="59b1f-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="59b1f-125">Si no se `EndCustomDump` llama a, se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="59b1f-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b1f-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59b1f-126">Requirements</span></span>  
 <span data-ttu-id="59b1f-127">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59b1f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59b1f-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="59b1f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59b1f-129">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="59b1f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59b1f-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59b1f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b1f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="59b1f-131">See also</span></span>

- [<span data-ttu-id="59b1f-132">CustomDumpItem (estructura)</span><span class="sxs-lookup"><span data-stu-id="59b1f-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="59b1f-133">ECustomDumpFlavor (enumeración)</span><span class="sxs-lookup"><span data-stu-id="59b1f-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="59b1f-134">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="59b1f-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
