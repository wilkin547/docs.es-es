---
description: 'Más información sobre: IActionOnCLREvent (interfaz)'
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
ms.openlocfilehash: 9d762635247f897663f4c6f2badf67edf98bd5d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785177"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="1c89f-103">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c89f-103">IActionOnCLREvent Interface</span></span>

<span data-ttu-id="1c89f-104">Proporciona el método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) , que realiza las devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1c89f-104">Provides the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c89f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1c89f-105">Methods</span></span>  
  
|<span data-ttu-id="1c89f-106">Método</span><span class="sxs-lookup"><span data-stu-id="1c89f-106">Method</span></span>|<span data-ttu-id="1c89f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c89f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c89f-108">Método OnEvent</span><span class="sxs-lookup"><span data-stu-id="1c89f-108">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="1c89f-109">Realiza una devolución de llamada para un evento registrado.</span><span class="sxs-lookup"><span data-stu-id="1c89f-109">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c89f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c89f-110">Requirements</span></span>  

 <span data-ttu-id="1c89f-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c89f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c89f-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1c89f-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c89f-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c89f-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c89f-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c89f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c89f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c89f-115">See also</span></span>

- [<span data-ttu-id="1c89f-116">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1c89f-116">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="1c89f-117">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c89f-117">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="1c89f-118">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c89f-118">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="1c89f-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1c89f-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
