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
ms.openlocfilehash: 9fd299ad25166bcbcf0202da13a5b4cbdd20d7d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133802"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="d97d3-102">IHostIoCompletionManager::InitializeHostOverlapped (Método)</span><span class="sxs-lookup"><span data-stu-id="d97d3-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="d97d3-103">Proporciona al host la oportunidad de inicializar los datos personalizados que se van a anexar a una estructura de `OVERLAPPED` de Win32 que se usa para las solicitudes de e/s asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="d97d3-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d97d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d97d3-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d97d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d97d3-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="d97d3-106">de Puntero a la estructura de `OVERLAPPED` de Win32 que se va a incluir con la solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="d97d3-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d97d3-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d97d3-107">Return Value</span></span>  
  
|<span data-ttu-id="d97d3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d97d3-108">HRESULT</span></span>|<span data-ttu-id="d97d3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d97d3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d97d3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d97d3-110">S_OK</span></span>|<span data-ttu-id="d97d3-111">`InitializeHostOverlapped` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d97d3-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="d97d3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d97d3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d97d3-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d97d3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d97d3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d97d3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d97d3-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d97d3-115">The call timed out.</span></span>|  
|<span data-ttu-id="d97d3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d97d3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d97d3-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d97d3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d97d3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d97d3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d97d3-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="d97d3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d97d3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d97d3-120">E_FAIL</span></span>|<span data-ttu-id="d97d3-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="d97d3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d97d3-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d97d3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d97d3-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d97d3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d97d3-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d97d3-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d97d3-125">No hay suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="d97d3-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d97d3-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d97d3-126">Remarks</span></span>  
 <span data-ttu-id="d97d3-127">Las funciones de la plataforma Windows usan la estructura `OVERLAPPED` para almacenar el estado de las solicitudes de e/s asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="d97d3-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="d97d3-128">CLR llama al método `InitializeHostOverlapped` para ofrecer al host la oportunidad de anexar datos personalizados a una instancia de `OVERLAPPED`.</span><span class="sxs-lookup"><span data-stu-id="d97d3-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d97d3-129">Para ir al principio de su bloque de datos personalizado, los hosts deben establecer el desplazamiento en el tamaño de la estructura de `OVERLAPPED` (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="d97d3-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="d97d3-130">Un valor devuelto de E_OUTOFMEMORY indica que el host no pudo inicializar sus datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="d97d3-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="d97d3-131">En este caso, CLR informa de un error y produce un error en la llamada.</span><span class="sxs-lookup"><span data-stu-id="d97d3-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d97d3-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d97d3-132">Requirements</span></span>  
 <span data-ttu-id="d97d3-133">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d97d3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d97d3-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d97d3-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d97d3-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d97d3-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d97d3-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d97d3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d97d3-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="d97d3-137">See also</span></span>

- [<span data-ttu-id="d97d3-138">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d97d3-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="d97d3-139">GetHostOverlappedSize (método)</span><span class="sxs-lookup"><span data-stu-id="d97d3-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="d97d3-140">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d97d3-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
