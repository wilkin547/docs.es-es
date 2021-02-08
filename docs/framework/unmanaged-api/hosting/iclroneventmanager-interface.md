---
description: 'Más información acerca de: ICLROnEventManager (interfaz)'
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
ms.openlocfilehash: 7a9c0beec5083bc93f5361bb0e701da5beeedea2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789832"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="c2884-103">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2884-103">ICLROnEventManager Interface</span></span>

<span data-ttu-id="c2884-104">Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c2884-104">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2884-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c2884-105">Methods</span></span>  
  
|<span data-ttu-id="c2884-106">Método</span><span class="sxs-lookup"><span data-stu-id="c2884-106">Method</span></span>|<span data-ttu-id="c2884-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2884-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2884-108">Método RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="c2884-108">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="c2884-109">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="c2884-109">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="c2884-110">Método UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="c2884-110">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="c2884-111">Anula el registro de un puntero de devolución de llamada registrado previamente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="c2884-111">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2884-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c2884-112">Remarks</span></span>  

 <span data-ttu-id="c2884-113">Para registrar y anular el registro de las devoluciones de llamada de eventos, el host obtiene una referencia a llamando al `ICLROnEventManager` método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c2884-113">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2884-114">Los eventos descritos por [EClrEvent](eclrevent-enumeration.md) se pueden desencadenar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="c2884-114">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2884-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2884-115">Requirements</span></span>  

 <span data-ttu-id="c2884-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2884-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2884-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c2884-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2884-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2884-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2884-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2884-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2884-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2884-120">See also</span></span>

- [<span data-ttu-id="c2884-121">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c2884-121">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="c2884-122">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2884-122">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="c2884-123">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2884-123">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="c2884-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c2884-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
