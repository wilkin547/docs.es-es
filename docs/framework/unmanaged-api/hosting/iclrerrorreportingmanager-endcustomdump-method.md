---
description: 'Más información acerca de: ICLRErrorReportingManager:: EndCustomDump (método)'
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
ms.openlocfilehash: 406d7d77f4cd63c69fec56acb0819d56c6271630
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689474"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="ecf54-103">ICLRErrorReportingManager::EndCustomDump (Método)</span><span class="sxs-lookup"><span data-stu-id="ecf54-103">ICLRErrorReportingManager::EndCustomDump Method</span></span>

<span data-ttu-id="ecf54-104">Quita la configuración de volcado de la pila personalizada que se especificó en una llamada anterior al método [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ecf54-104">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecf54-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecf54-105">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ecf54-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ecf54-106">Return Value</span></span>  
  
|<span data-ttu-id="ecf54-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ecf54-107">HRESULT</span></span>|<span data-ttu-id="ecf54-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecf54-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ecf54-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="ecf54-109">S_OK</span></span>|<span data-ttu-id="ecf54-110">`EndCustomDump` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ecf54-110">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="ecf54-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ecf54-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ecf54-112">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ecf54-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ecf54-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ecf54-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ecf54-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ecf54-114">The call timed out.</span></span>|  
|<span data-ttu-id="ecf54-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ecf54-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ecf54-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ecf54-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ecf54-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ecf54-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ecf54-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ecf54-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ecf54-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ecf54-119">E_FAIL</span></span>|<span data-ttu-id="ecf54-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ecf54-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ecf54-121">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ecf54-121">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ecf54-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ecf54-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecf54-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ecf54-123">Remarks</span></span>  

 <span data-ttu-id="ecf54-124">El `EndCustomDump` método borra la configuración de volcado de pila personalizada establecida por una llamada anterior al `BeginCustomDump` método y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="ecf54-124">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="ecf54-125">Se debe llamar después de completar el volcado de la pila personalizado.</span><span class="sxs-lookup"><span data-stu-id="ecf54-125">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ecf54-126">Si no se llama a `EndCustomDump` , se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="ecf54-126">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecf54-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecf54-127">Requirements</span></span>  

 <span data-ttu-id="ecf54-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecf54-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecf54-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ecf54-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ecf54-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ecf54-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecf54-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecf54-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf54-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecf54-132">See also</span></span>

- [<span data-ttu-id="ecf54-133">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ecf54-133">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="ecf54-134">ECustomDumpFlavor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ecf54-134">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="ecf54-135">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ecf54-135">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
