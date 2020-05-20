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
ms.openlocfilehash: 4e72cd8bee2cb4f35155d7b99cfe8d9cf63f463a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616078"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="e9a35-102">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9a35-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="e9a35-103">Proporciona el método [IActionOnCLREvent:: onEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) , que realiza las devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e9a35-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9a35-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e9a35-104">Methods</span></span>  
  
|<span data-ttu-id="e9a35-105">Método</span><span class="sxs-lookup"><span data-stu-id="e9a35-105">Method</span></span>|<span data-ttu-id="e9a35-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9a35-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9a35-107">Método OnEvent</span><span class="sxs-lookup"><span data-stu-id="e9a35-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="e9a35-108">Realiza una devolución de llamada para un evento registrado.</span><span class="sxs-lookup"><span data-stu-id="e9a35-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9a35-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9a35-109">Requirements</span></span>  
 <span data-ttu-id="e9a35-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9a35-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a35-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e9a35-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9a35-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e9a35-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9a35-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a35-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a35-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="e9a35-114">See also</span></span>

- [<span data-ttu-id="e9a35-115">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e9a35-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="e9a35-116">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9a35-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e9a35-117">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9a35-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="e9a35-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e9a35-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
