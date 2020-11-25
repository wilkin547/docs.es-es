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
ms.openlocfilehash: 8ca4bb1fe35451f95f752a4e71f5f0b541b55e58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721782"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="94f51-102">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94f51-102">IActionOnCLREvent Interface</span></span>

<span data-ttu-id="94f51-103">Proporciona el método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) , que realiza las devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="94f51-103">Provides the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94f51-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="94f51-104">Methods</span></span>  
  
|<span data-ttu-id="94f51-105">Método</span><span class="sxs-lookup"><span data-stu-id="94f51-105">Method</span></span>|<span data-ttu-id="94f51-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="94f51-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94f51-107">Método OnEvent</span><span class="sxs-lookup"><span data-stu-id="94f51-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="94f51-108">Realiza una devolución de llamada para un evento registrado.</span><span class="sxs-lookup"><span data-stu-id="94f51-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94f51-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94f51-109">Requirements</span></span>  

 <span data-ttu-id="94f51-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94f51-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94f51-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="94f51-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94f51-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94f51-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94f51-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94f51-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f51-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94f51-114">See also</span></span>

- [<span data-ttu-id="94f51-115">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="94f51-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="94f51-116">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94f51-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="94f51-117">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94f51-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="94f51-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="94f51-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
