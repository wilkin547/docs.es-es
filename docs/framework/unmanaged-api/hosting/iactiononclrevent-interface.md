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
ms.openlocfilehash: f577e9252d97ec188ff1076fd8340336b16c8257
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504334"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="118cc-102">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="118cc-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="118cc-103">Proporciona el método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) , que realiza las devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="118cc-103">Provides the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="118cc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="118cc-104">Methods</span></span>  
  
|<span data-ttu-id="118cc-105">Método</span><span class="sxs-lookup"><span data-stu-id="118cc-105">Method</span></span>|<span data-ttu-id="118cc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="118cc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="118cc-107">Método OnEvent</span><span class="sxs-lookup"><span data-stu-id="118cc-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="118cc-108">Realiza una devolución de llamada para un evento registrado.</span><span class="sxs-lookup"><span data-stu-id="118cc-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="118cc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="118cc-109">Requirements</span></span>  
 <span data-ttu-id="118cc-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="118cc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="118cc-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="118cc-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="118cc-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="118cc-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="118cc-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="118cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118cc-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="118cc-114">See also</span></span>

- [<span data-ttu-id="118cc-115">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="118cc-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="118cc-116">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="118cc-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="118cc-117">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="118cc-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="118cc-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="118cc-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
