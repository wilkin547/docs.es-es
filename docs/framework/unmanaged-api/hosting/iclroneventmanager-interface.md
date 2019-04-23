---
title: ICLROnEventManager (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7486a094deab16ebbc05f19f1b652126479ce11c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183006"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="8b0ea-102">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b0ea-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="8b0ea-103">Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8b0ea-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b0ea-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8b0ea-104">Methods</span></span>  
  
|<span data-ttu-id="8b0ea-105">Método</span><span class="sxs-lookup"><span data-stu-id="8b0ea-105">Method</span></span>|<span data-ttu-id="8b0ea-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b0ea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b0ea-107">RegisterActionOnEvent (método)</span><span class="sxs-lookup"><span data-stu-id="8b0ea-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="8b0ea-108">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="8b0ea-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="8b0ea-109">UnregisterActionOnEvent (método)</span><span class="sxs-lookup"><span data-stu-id="8b0ea-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="8b0ea-110">Anula el registro de un puntero de devolución de llamada registrada anteriormente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="8b0ea-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b0ea-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8b0ea-111">Remarks</span></span>  
 <span data-ttu-id="8b0ea-112">Para registrar y anular el registro de las devoluciones de llamada de evento, el host obtiene una referencia a `ICLROnEventManager` mediante una llamada a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="8b0ea-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b0ea-113">Los eventos descritos por [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) pueden activar más de una vez y desde diferentes subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="8b0ea-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b0ea-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b0ea-114">Requirements</span></span>  
 <span data-ttu-id="8b0ea-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b0ea-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b0ea-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b0ea-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b0ea-117">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b0ea-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b0ea-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b0ea-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b0ea-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b0ea-119">See also</span></span>

- [<span data-ttu-id="8b0ea-120">EClrEvent (enumeración)</span><span class="sxs-lookup"><span data-stu-id="8b0ea-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="8b0ea-121">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b0ea-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="8b0ea-122">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b0ea-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="8b0ea-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8b0ea-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
