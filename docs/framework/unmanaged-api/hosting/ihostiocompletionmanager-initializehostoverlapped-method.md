---
description: 'Más información sobre: IHostIoCompletionManager:: Initializehostoverlapped ((método)'
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
ms.openlocfilehash: 10be7edb67143937dec6efc6e35466466374d32d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708468"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="d575e-103">IHostIoCompletionManager::InitializeHostOverlapped (Método)</span><span class="sxs-lookup"><span data-stu-id="d575e-103">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>

<span data-ttu-id="d575e-104">Proporciona al host la oportunidad de inicializar los datos personalizados que se van a anexar a una `OVERLAPPED` estructura de Win32 que se usa para las solicitudes de e/s asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="d575e-104">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d575e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d575e-105">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d575e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d575e-106">Parameters</span></span>  

 `pvOverlapped`  
 <span data-ttu-id="d575e-107">de Puntero a la estructura de Win32 `OVERLAPPED` que se va a incluir con la solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="d575e-107">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d575e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d575e-108">Return Value</span></span>  
  
|<span data-ttu-id="d575e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d575e-109">HRESULT</span></span>|<span data-ttu-id="d575e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d575e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d575e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d575e-111">S_OK</span></span>|<span data-ttu-id="d575e-112">`InitializeHostOverlapped` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d575e-112">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="d575e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d575e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d575e-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d575e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d575e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d575e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d575e-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d575e-116">The call timed out.</span></span>|  
|<span data-ttu-id="d575e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d575e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d575e-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d575e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d575e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d575e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d575e-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="d575e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d575e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d575e-121">E_FAIL</span></span>|<span data-ttu-id="d575e-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="d575e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d575e-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d575e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d575e-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d575e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d575e-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d575e-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d575e-126">No hay suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="d575e-126">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d575e-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d575e-127">Remarks</span></span>  

 <span data-ttu-id="d575e-128">Las funciones de la plataforma Windows usan la `OVERLAPPED` estructura para almacenar el estado de las solicitudes de e/s asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="d575e-128">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="d575e-129">CLR llama al `InitializeHostOverlapped` método para proporcionar al host la oportunidad de anexar datos personalizados a una `OVERLAPPED` instancia de.</span><span class="sxs-lookup"><span data-stu-id="d575e-129">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d575e-130">Para llegar al principio de su bloque de datos personalizado, los hosts deben establecer el desplazamiento en el tamaño de la `OVERLAPPED` estructura ( `sizeof(OVERLAPPED)` ).</span><span class="sxs-lookup"><span data-stu-id="d575e-130">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="d575e-131">Un valor devuelto de E_OUTOFMEMORY indica que el host no pudo inicializar sus datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="d575e-131">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="d575e-132">En este caso, CLR informa de un error y produce un error en la llamada.</span><span class="sxs-lookup"><span data-stu-id="d575e-132">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d575e-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d575e-133">Requirements</span></span>  

 <span data-ttu-id="d575e-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d575e-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d575e-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d575e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d575e-136">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d575e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d575e-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d575e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d575e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d575e-138">See also</span></span>

- [<span data-ttu-id="d575e-139">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d575e-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="d575e-140">Método GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="d575e-140">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="d575e-141">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d575e-141">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
