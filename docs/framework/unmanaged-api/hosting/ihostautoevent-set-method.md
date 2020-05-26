---
title: IHostAutoEvent::Set (Método)
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
ms.openlocfilehash: 55fd858927743b097e5e842c0897a16d36b76733
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804982"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="acce9-102">IHostAutoEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="acce9-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="acce9-103">Establece la instancia de [IHostAutoEvent](ihostautoevent-interface.md) actual en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="acce9-103">Sets the current [IHostAutoEvent](ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acce9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acce9-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="acce9-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="acce9-105">Return Value</span></span>  
  
|<span data-ttu-id="acce9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="acce9-106">HRESULT</span></span>|<span data-ttu-id="acce9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="acce9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="acce9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="acce9-108">S_OK</span></span>|<span data-ttu-id="acce9-109">`Set`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="acce9-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="acce9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="acce9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="acce9-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="acce9-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="acce9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="acce9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="acce9-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="acce9-113">The call timed out.</span></span>|  
|<span data-ttu-id="acce9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="acce9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="acce9-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="acce9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="acce9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="acce9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="acce9-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="acce9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="acce9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="acce9-118">E_FAIL</span></span>|<span data-ttu-id="acce9-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="acce9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="acce9-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="acce9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="acce9-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="acce9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acce9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acce9-122">Requirements</span></span>  
 <span data-ttu-id="acce9-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acce9-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acce9-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="acce9-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acce9-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="acce9-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acce9-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acce9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acce9-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acce9-127">See also</span></span>

- [<span data-ttu-id="acce9-128">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="acce9-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="acce9-129">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="acce9-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="acce9-130">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="acce9-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="acce9-131">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="acce9-131">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
