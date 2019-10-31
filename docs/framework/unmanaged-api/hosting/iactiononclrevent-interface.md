---
title: IActionOnCLREvent (Interfaz)
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: 9277fe2c241ce4f502339de826dccd08a2ce8055
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126957"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="0e48a-102">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e48a-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="0e48a-103">Proporciona el método [IActionOnCLREvent:: onEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) , que realiza las devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0e48a-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e48a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0e48a-104">Methods</span></span>  
  
|<span data-ttu-id="0e48a-105">Método</span><span class="sxs-lookup"><span data-stu-id="0e48a-105">Method</span></span>|<span data-ttu-id="0e48a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e48a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e48a-107">OnEvent (método)</span><span class="sxs-lookup"><span data-stu-id="0e48a-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="0e48a-108">Realiza una devolución de llamada para un evento registrado.</span><span class="sxs-lookup"><span data-stu-id="0e48a-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e48a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e48a-109">Requirements</span></span>  
 <span data-ttu-id="0e48a-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e48a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e48a-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0e48a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e48a-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0e48a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e48a-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e48a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e48a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e48a-114">See also</span></span>

- [<span data-ttu-id="0e48a-115">EClrEvent (enumeración)</span><span class="sxs-lookup"><span data-stu-id="0e48a-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="0e48a-116">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e48a-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0e48a-117">ICLROnEventManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e48a-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="0e48a-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0e48a-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
