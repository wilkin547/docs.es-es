---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 899d0cf6a0475846b749bd0b7cbda41b1b88253d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949701"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="d792c-102">ICLRMemoryNotificationCallback::OnMemoryNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="d792c-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="d792c-103">Notifica al Common Language Runtime (CLR) la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d792c-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d792c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d792c-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d792c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d792c-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="d792c-106">de Uno de los valores de [ememoryavailable (](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) , que indica la presión de memoria que el equipo está experimentando actualmente.</span><span class="sxs-lookup"><span data-stu-id="d792c-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d792c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d792c-107">Return Value</span></span>  
  
|<span data-ttu-id="d792c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d792c-108">HRESULT</span></span>|<span data-ttu-id="d792c-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d792c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d792c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d792c-110">S_OK</span></span>|<span data-ttu-id="d792c-111">`OnMemoryNotification`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d792c-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="d792c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d792c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d792c-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d792c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d792c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d792c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d792c-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d792c-115">The call timed out.</span></span>|  
|<span data-ttu-id="d792c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d792c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d792c-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d792c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d792c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d792c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d792c-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="d792c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d792c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d792c-120">E_FAIL</span></span>|<span data-ttu-id="d792c-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="d792c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d792c-122">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d792c-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d792c-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d792c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d792c-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d792c-124">Remarks</span></span>  
 <span data-ttu-id="d792c-125">CLR registra una devolución de llamada en `OnMemoryNotification` mediante una llamada al método [IHostMemoryManager:: RegisterMemoryNotificationCallback (](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d792c-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="d792c-126">El motor en tiempo de ejecución usa la información devuelta en la devolución de llamada para liberar memoria adicional cuando el host informa de que los recursos de memoria se están agotando.</span><span class="sxs-lookup"><span data-stu-id="d792c-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d792c-127">Las llamadas `OnMemoryNotification` a no se bloquean nunca.</span><span class="sxs-lookup"><span data-stu-id="d792c-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="d792c-128">Siempre devuelven inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="d792c-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d792c-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d792c-129">Requirements</span></span>  
 <span data-ttu-id="d792c-130">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d792c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d792c-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d792c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d792c-132">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d792c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d792c-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d792c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d792c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d792c-134">See also</span></span>

- [<span data-ttu-id="d792c-135">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d792c-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="d792c-136">RegisterMemoryNotificationCallback (método)</span><span class="sxs-lookup"><span data-stu-id="d792c-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="d792c-137">ICLRMemoryNotificationCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d792c-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
