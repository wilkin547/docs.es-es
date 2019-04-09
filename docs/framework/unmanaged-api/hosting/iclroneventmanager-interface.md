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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183006"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="d6340-102">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6340-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="d6340-103">Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d6340-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6340-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d6340-104">Methods</span></span>  
  
|<span data-ttu-id="d6340-105">Método</span><span class="sxs-lookup"><span data-stu-id="d6340-105">Method</span></span>|<span data-ttu-id="d6340-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6340-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6340-107">Método RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="d6340-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="d6340-108">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="d6340-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="d6340-109">Método UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="d6340-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="d6340-110">Anula el registro de un puntero de devolución de llamada registrada anteriormente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="d6340-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6340-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6340-111">Remarks</span></span>  
 <span data-ttu-id="d6340-112">Para registrar y anular el registro de las devoluciones de llamada de evento, el host obtiene una referencia a `ICLROnEventManager` mediante una llamada a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d6340-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6340-113">Los eventos descritos por [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) pueden activar más de una vez y desde diferentes subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="d6340-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6340-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6340-114">Requirements</span></span>  
 <span data-ttu-id="d6340-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6340-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6340-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d6340-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d6340-117">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6340-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d6340-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d6340-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d6340-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6340-119">See also</span></span>

- [<span data-ttu-id="d6340-120">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d6340-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="d6340-121">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6340-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="d6340-122">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6340-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d6340-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d6340-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
