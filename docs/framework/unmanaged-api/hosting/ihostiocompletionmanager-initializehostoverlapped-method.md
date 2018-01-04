---
title: "IHostIoCompletionManager::InitializeHostOverlapped (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.InitializeHostOverlapped
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b558d638e598ba6e3d0055e3a842976896e99d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="7fab8-102">IHostIoCompletionManager::InitializeHostOverlapped (Método)</span><span class="sxs-lookup"><span data-stu-id="7fab8-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="7fab8-103">Ofrece al host la oportunidad de inicializar los datos personalizados para anexar a Win32 `OVERLAPPED` estructura que se utiliza para solicitudes de E/S asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="7fab8-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fab8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fab8-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fab8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7fab8-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="7fab8-106">[in] Un puntero a la de Win32 `OVERLAPPED` estructura que se incluya con la solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="7fab8-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fab8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7fab8-107">Return Value</span></span>  
  
|<span data-ttu-id="7fab8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7fab8-108">HRESULT</span></span>|<span data-ttu-id="7fab8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fab8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7fab8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7fab8-110">S_OK</span></span>|<span data-ttu-id="7fab8-111">`InitializeHostOverlapped`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7fab8-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="7fab8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7fab8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7fab8-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7fab8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7fab8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7fab8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7fab8-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7fab8-115">The call timed out.</span></span>|  
|<span data-ttu-id="7fab8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fab8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7fab8-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7fab8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7fab8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7fab8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7fab8-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="7fab8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7fab8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7fab8-120">E_FAIL</span></span>|<span data-ttu-id="7fab8-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="7fab8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7fab8-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7fab8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7fab8-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7fab8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7fab8-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7fab8-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7fab8-125">No había memoria suficiente disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="7fab8-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fab8-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7fab8-126">Remarks</span></span>  
 <span data-ttu-id="7fab8-127">Funciones de la plataforma de Windows utilizan el `OVERLAPPED` estructura para almacenar el estado de solicitudes de E/S asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="7fab8-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="7fab8-128">CLR llama el `InitializeHostOverlapped` método para dar al host la oportunidad de anexar datos personalizados a un `OVERLAPPED` instancia.</span><span class="sxs-lookup"><span data-stu-id="7fab8-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7fab8-129">Para ir al principio del bloque de datos personalizado, los hosts deben establecer el desplazamiento al tamaño de la `OVERLAPPED` estructura (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="7fab8-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="7fab8-130">Un valor devuelto de E_OUTOFMEMORY indica que el host ha podido inicializar sus datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="7fab8-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="7fab8-131">En este caso, CLR notifica un error y produce un error en la llamada.</span><span class="sxs-lookup"><span data-stu-id="7fab8-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fab8-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fab8-132">Requirements</span></span>  
 <span data-ttu-id="7fab8-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fab8-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fab8-134">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7fab8-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7fab8-135">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7fab8-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7fab8-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fab8-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fab8-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fab8-137">See Also</span></span>  
 [<span data-ttu-id="7fab8-138">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fab8-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="7fab8-139">GetHostOverlappedSize (método)</span><span class="sxs-lookup"><span data-stu-id="7fab8-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)  
 [<span data-ttu-id="7fab8-140">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fab8-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
