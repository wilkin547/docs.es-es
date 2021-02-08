---
description: 'Más información acerca de: ICLRMemoryNotificationCallback:: OnMemoryNotification (método)'
title: ICLRMemoryNotificationCallback::OnMemoryNotification (Método)
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
ms.openlocfilehash: 92041c433fa82bb63afda7968eb8c6e1fa72acb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789921"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="232e3-103">ICLRMemoryNotificationCallback::OnMemoryNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="232e3-103">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>

<span data-ttu-id="232e3-104">Notifica al Common Language Runtime (CLR) la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="232e3-104">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="232e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="232e3-105">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="232e3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="232e3-106">Parameters</span></span>  

 `eMemoryAvailable`  
 <span data-ttu-id="232e3-107">de Uno de los valores de [ememoryavailable (](ememoryavailable-enumeration.md) , que indica la presión de memoria que el equipo está experimentando actualmente.</span><span class="sxs-lookup"><span data-stu-id="232e3-107">[in] One of the [EMemoryAvailable](ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="232e3-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="232e3-108">Return Value</span></span>  
  
|<span data-ttu-id="232e3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="232e3-109">HRESULT</span></span>|<span data-ttu-id="232e3-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="232e3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="232e3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="232e3-111">S_OK</span></span>|<span data-ttu-id="232e3-112">`OnMemoryNotification` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="232e3-112">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="232e3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="232e3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="232e3-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="232e3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="232e3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="232e3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="232e3-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="232e3-116">The call timed out.</span></span>|  
|<span data-ttu-id="232e3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="232e3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="232e3-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="232e3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="232e3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="232e3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="232e3-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="232e3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="232e3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="232e3-121">E_FAIL</span></span>|<span data-ttu-id="232e3-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="232e3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="232e3-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="232e3-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="232e3-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="232e3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="232e3-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="232e3-125">Remarks</span></span>  

 <span data-ttu-id="232e3-126">CLR registra una devolución de llamada en `OnMemoryNotification` mediante una llamada al método [IHostMemoryManager:: RegisterMemoryNotificationCallback (](ihostmemorymanager-registermemorynotificationcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="232e3-126">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="232e3-127">El motor en tiempo de ejecución usa la información devuelta en la devolución de llamada para liberar memoria adicional cuando el host informa de que los recursos de memoria se están agotando.</span><span class="sxs-lookup"><span data-stu-id="232e3-127">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="232e3-128">Las llamadas a no se `OnMemoryNotification` bloquean nunca.</span><span class="sxs-lookup"><span data-stu-id="232e3-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="232e3-129">Siempre devuelven inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="232e3-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="232e3-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="232e3-130">Requirements</span></span>  

 <span data-ttu-id="232e3-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="232e3-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="232e3-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="232e3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="232e3-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="232e3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="232e3-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="232e3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="232e3-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="232e3-135">See also</span></span>

- [<span data-ttu-id="232e3-136">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="232e3-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="232e3-137">Método RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="232e3-137">RegisterMemoryNotificationCallback Method</span></span>](ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="232e3-138">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="232e3-138">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
