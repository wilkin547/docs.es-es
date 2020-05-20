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
ms.openlocfilehash: 30312e6e09535cee2968b1f9e8ac87b461c5ff40
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703521"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="8c05e-102">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c05e-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="8c05e-103">Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8c05e-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c05e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8c05e-104">Methods</span></span>  
  
|<span data-ttu-id="8c05e-105">Método</span><span class="sxs-lookup"><span data-stu-id="8c05e-105">Method</span></span>|<span data-ttu-id="8c05e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c05e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8c05e-107">Método RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="8c05e-107">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="8c05e-108">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="8c05e-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="8c05e-109">Método UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="8c05e-109">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="8c05e-110">Anula el registro de un puntero de devolución de llamada registrado previamente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="8c05e-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c05e-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8c05e-111">Remarks</span></span>  
 <span data-ttu-id="8c05e-112">Para registrar y anular el registro de las devoluciones de llamada de eventos, el host obtiene una referencia a llamando al `ICLROnEventManager` método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8c05e-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c05e-113">Los eventos descritos por [EClrEvent](eclrevent-enumeration.md) se pueden desencadenar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="8c05e-113">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c05e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c05e-114">Requirements</span></span>  
 <span data-ttu-id="8c05e-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c05e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c05e-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8c05e-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c05e-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8c05e-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c05e-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c05e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c05e-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="8c05e-119">See also</span></span>

- [<span data-ttu-id="8c05e-120">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8c05e-120">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="8c05e-121">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c05e-121">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="8c05e-122">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c05e-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="8c05e-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8c05e-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
