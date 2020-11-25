---
title: ICLRIoCompletionManager::OnComplete (Método)
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: 15119974acf74b49669e5ffbee59fbff9e5c84c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714112"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="7ff75-102">ICLRIoCompletionManager::OnComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="7ff75-102">ICLRIoCompletionManager::OnComplete Method</span></span>

<span data-ttu-id="7ff75-103">Notifica al Common Language Runtime (CLR) el estado de una solicitud de e/s realizada mediante una llamada al método [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7ff75-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ff75-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ff75-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ff75-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ff75-105">Parameters</span></span>  

 `dwErrorCode`  
 <span data-ttu-id="7ff75-106">de Un valor HRESULT que indica el estado de la operación de enlace.</span><span class="sxs-lookup"><span data-stu-id="7ff75-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="7ff75-107">S_OK indica que la operación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ff75-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="7ff75-108">HOST_E_INTERRUPTED indica que la llamada finalizó antes de la finalización.</span><span class="sxs-lookup"><span data-stu-id="7ff75-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="7ff75-109">E_FAIL indica que se ha producido un error grave desconocido irrecuperable.</span><span class="sxs-lookup"><span data-stu-id="7ff75-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="7ff75-110">de Número de bytes transferidos durante el procesamiento de la solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="7ff75-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="7ff75-111">de Puntero a la `OVERLAPPED` estructura que se pasó a la llamada al `IHostIoCompletionManager::Bind` método.</span><span class="sxs-lookup"><span data-stu-id="7ff75-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ff75-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7ff75-112">Return Value</span></span>  
  
|<span data-ttu-id="7ff75-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ff75-113">HRESULT</span></span>|<span data-ttu-id="7ff75-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ff75-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7ff75-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ff75-115">S_OK</span></span>|<span data-ttu-id="7ff75-116">`OnComplete` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ff75-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="7ff75-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7ff75-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7ff75-118">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ff75-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7ff75-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7ff75-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7ff75-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7ff75-120">The call timed out.</span></span>|  
|<span data-ttu-id="7ff75-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7ff75-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7ff75-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7ff75-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7ff75-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7ff75-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7ff75-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="7ff75-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7ff75-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7ff75-125">E_FAIL</span></span>|<span data-ttu-id="7ff75-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7ff75-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7ff75-127">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7ff75-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7ff75-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7ff75-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ff75-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ff75-129">Remarks</span></span>  

 <span data-ttu-id="7ff75-130">Si el host implementa una abstracción de finalización de e/s, el CLR realiza solicitudes de e/s a través del host mediante el uso de métodos de [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7ff75-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="7ff75-131">Después, el host llama al `OnComplete` método para notificar al tiempo de ejecución el resultado de dichas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="7ff75-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ff75-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ff75-132">Requirements</span></span>  

 <span data-ttu-id="7ff75-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ff75-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ff75-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7ff75-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ff75-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ff75-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ff75-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ff75-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff75-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ff75-137">See also</span></span>

- [<span data-ttu-id="7ff75-138">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ff75-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="7ff75-139">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ff75-139">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="7ff75-140">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ff75-140">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
