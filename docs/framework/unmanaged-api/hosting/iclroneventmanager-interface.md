---
title: ICLROnEventManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 02a19a3daf72cdfa493b09fa984fe7b50865ed30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="a2559-102">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2559-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="a2559-103">Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada de eventos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a2559-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2559-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a2559-104">Methods</span></span>  
  
|<span data-ttu-id="a2559-105">Método</span><span class="sxs-lookup"><span data-stu-id="a2559-105">Method</span></span>|<span data-ttu-id="a2559-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2559-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2559-107">RegisterActionOnEvent (método)</span><span class="sxs-lookup"><span data-stu-id="a2559-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="a2559-108">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="a2559-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="a2559-109">UnregisterActionOnEvent (método)</span><span class="sxs-lookup"><span data-stu-id="a2559-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="a2559-110">Anula el registro de un puntero de devolución de llamada registrada anteriormente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="a2559-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2559-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2559-111">Remarks</span></span>  
 <span data-ttu-id="a2559-112">Para registrar y anular el registro de las devoluciones de llamada de evento, el host obtiene una referencia a `ICLROnEventManager` mediante una llamada a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a2559-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2559-113">Los eventos descritos por [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) pueden desencadenarse varias veces y desde subprocesos diferentes para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="a2559-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2559-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2559-114">Requirements</span></span>  
 <span data-ttu-id="a2559-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2559-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2559-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2559-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2559-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2559-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2559-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2559-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2559-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2559-119">See Also</span></span>  
 [<span data-ttu-id="a2559-120">EClrEvent (enumeración)</span><span class="sxs-lookup"><span data-stu-id="a2559-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="a2559-121">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2559-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="a2559-122">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2559-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="a2559-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a2559-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
