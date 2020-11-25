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
ms.openlocfilehash: 1948075d87b5a44397a1eaab3adb4edbc96d7143
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725643"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="b7f2f-102">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7f2f-102">ICLROnEventManager Interface</span></span>

<span data-ttu-id="b7f2f-103">Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b7f2f-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7f2f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b7f2f-104">Methods</span></span>  
  
|<span data-ttu-id="b7f2f-105">Método</span><span class="sxs-lookup"><span data-stu-id="b7f2f-105">Method</span></span>|<span data-ttu-id="b7f2f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7f2f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7f2f-107">Método RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="b7f2f-107">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="b7f2f-108">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="b7f2f-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="b7f2f-109">Método UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="b7f2f-109">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="b7f2f-110">Anula el registro de un puntero de devolución de llamada registrado previamente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="b7f2f-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7f2f-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7f2f-111">Remarks</span></span>  

 <span data-ttu-id="b7f2f-112">Para registrar y anular el registro de las devoluciones de llamada de eventos, el host obtiene una referencia a llamando al `ICLROnEventManager` método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b7f2f-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7f2f-113">Los eventos descritos por [EClrEvent](eclrevent-enumeration.md) se pueden desencadenar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="b7f2f-113">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7f2f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7f2f-114">Requirements</span></span>  

 <span data-ttu-id="b7f2f-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7f2f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7f2f-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b7f2f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7f2f-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7f2f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7f2f-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7f2f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f2f-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7f2f-119">See also</span></span>

- [<span data-ttu-id="b7f2f-120">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b7f2f-120">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="b7f2f-121">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7f2f-121">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="b7f2f-122">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7f2f-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="b7f2f-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b7f2f-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
