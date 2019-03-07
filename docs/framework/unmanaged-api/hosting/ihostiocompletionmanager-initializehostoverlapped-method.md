---
title: IHostIoCompletionManager::InitializeHostOverlapped (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97d2959a27bb848d05dc44492152866b2d535b68
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503169"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="24ec9-102">IHostIoCompletionManager::InitializeHostOverlapped (Método)</span><span class="sxs-lookup"><span data-stu-id="24ec9-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="24ec9-103">Ofrece al host la oportunidad de inicializar los datos personalizados para anexar a Win32 `OVERLAPPED` estructura que se utiliza para solicitudes de E/S asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="24ec9-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ec9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24ec9-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24ec9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24ec9-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="24ec9-106">[in] Un puntero a Win32 `OVERLAPPED` estructura que se incluya con la solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="24ec9-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24ec9-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="24ec9-107">Return Value</span></span>  
  
|<span data-ttu-id="24ec9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24ec9-108">HRESULT</span></span>|<span data-ttu-id="24ec9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="24ec9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="24ec9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="24ec9-110">S_OK</span></span>|<span data-ttu-id="24ec9-111">`InitializeHostOverlapped` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="24ec9-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="24ec9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="24ec9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="24ec9-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="24ec9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="24ec9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="24ec9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="24ec9-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="24ec9-115">The call timed out.</span></span>|  
|<span data-ttu-id="24ec9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="24ec9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="24ec9-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="24ec9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="24ec9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="24ec9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="24ec9-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="24ec9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="24ec9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="24ec9-120">E_FAIL</span></span>|<span data-ttu-id="24ec9-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="24ec9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="24ec9-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="24ec9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="24ec9-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="24ec9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="24ec9-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="24ec9-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="24ec9-125">No había suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="24ec9-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24ec9-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24ec9-126">Remarks</span></span>  
 <span data-ttu-id="24ec9-127">Funciones de la plataforma de Windows utilizan el `OVERLAPPED` estructura para almacenar el estado de las solicitudes de E/S asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="24ec9-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="24ec9-128">CLR llama a la `InitializeHostOverlapped` método para dar al host la oportunidad de anexar datos personalizados a un `OVERLAPPED` instancia.</span><span class="sxs-lookup"><span data-stu-id="24ec9-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="24ec9-129">Para obtener al principio del bloque de datos personalizado, hosts deben establecerse el desplazamiento en el tamaño de la `OVERLAPPED` estructura (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="24ec9-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="24ec9-130">Un valor devuelto de E_OUTOFMEMORY indica que el host ha podido inicializar sus datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="24ec9-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="24ec9-131">En este caso, CLR notifica un error y se produce un error en la llamada.</span><span class="sxs-lookup"><span data-stu-id="24ec9-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24ec9-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24ec9-132">Requirements</span></span>  
 <span data-ttu-id="24ec9-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24ec9-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ec9-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="24ec9-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24ec9-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24ec9-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24ec9-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ec9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ec9-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="24ec9-137">See also</span></span>
- [<span data-ttu-id="24ec9-138">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24ec9-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="24ec9-139">GetHostOverlappedSize (método)</span><span class="sxs-lookup"><span data-stu-id="24ec9-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="24ec9-140">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24ec9-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
