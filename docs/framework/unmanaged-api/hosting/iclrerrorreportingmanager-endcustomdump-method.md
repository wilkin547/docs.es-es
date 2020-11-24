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
ms.openlocfilehash: feaeba15fcc4e8264f7fde57d3b268a6b583ad83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677840"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="3044b-102">ICLRErrorReportingManager::EndCustomDump (Método)</span><span class="sxs-lookup"><span data-stu-id="3044b-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>

<span data-ttu-id="3044b-103">Quita la configuración de volcado de la pila personalizada que se especificó en una llamada anterior al método [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3044b-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3044b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3044b-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3044b-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3044b-105">Return Value</span></span>  
  
|<span data-ttu-id="3044b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3044b-106">HRESULT</span></span>|<span data-ttu-id="3044b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3044b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3044b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3044b-108">S_OK</span></span>|<span data-ttu-id="3044b-109">`EndCustomDump` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3044b-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="3044b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3044b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3044b-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3044b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3044b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3044b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3044b-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3044b-113">The call timed out.</span></span>|  
|<span data-ttu-id="3044b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3044b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3044b-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3044b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3044b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3044b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3044b-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3044b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3044b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3044b-118">E_FAIL</span></span>|<span data-ttu-id="3044b-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3044b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3044b-120">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3044b-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3044b-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3044b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3044b-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3044b-122">Remarks</span></span>  

 <span data-ttu-id="3044b-123">El `EndCustomDump` método borra la configuración de volcado de pila personalizada establecida por una llamada anterior al `BeginCustomDump` método y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="3044b-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="3044b-124">Se debe llamar después de completar el volcado de la pila personalizado.</span><span class="sxs-lookup"><span data-stu-id="3044b-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3044b-125">Si no se llama a `EndCustomDump` , se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="3044b-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3044b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3044b-126">Requirements</span></span>  

 <span data-ttu-id="3044b-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3044b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3044b-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3044b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3044b-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3044b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3044b-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3044b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3044b-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3044b-131">See also</span></span>

- [<span data-ttu-id="3044b-132">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="3044b-132">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="3044b-133">ECustomDumpFlavor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3044b-133">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="3044b-134">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3044b-134">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
