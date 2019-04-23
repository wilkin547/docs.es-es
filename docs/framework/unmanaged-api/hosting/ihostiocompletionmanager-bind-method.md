---
title: IHostIoCompletionManager::Bind (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fa87026e0d4c93da782be15bef98afa9a0e4dfd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102471"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="410d9-102">IHostIoCompletionManager::Bind (Método)</span><span class="sxs-lookup"><span data-stu-id="410d9-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="410d9-103">El identificador especificado se enlaza a un puerto de terminación de E/S que se ha creado mediante una llamada anterior a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="410d9-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="410d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="410d9-104">Syntax</span></span>  
  
```  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="410d9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="410d9-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="410d9-106">[in] El puerto de terminación de E/S que se va a enlazar `hHandle`.</span><span class="sxs-lookup"><span data-stu-id="410d9-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="410d9-107">Si el valor de `hPort` es null, `hHandle` está enlazada para el puerto de terminación de E/S de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="410d9-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="410d9-108">[in] El identificador del sistema operativo para enlazar a `hPort`.</span><span class="sxs-lookup"><span data-stu-id="410d9-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="410d9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="410d9-109">Return Value</span></span>  
  
|<span data-ttu-id="410d9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="410d9-110">HRESULT</span></span>|<span data-ttu-id="410d9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="410d9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="410d9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="410d9-112">S_OK</span></span>|<span data-ttu-id="410d9-113">`Bind` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="410d9-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="410d9-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="410d9-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="410d9-115">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="410d9-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="410d9-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="410d9-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="410d9-117">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="410d9-117">The call timed out.</span></span>|  
|<span data-ttu-id="410d9-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="410d9-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="410d9-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="410d9-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="410d9-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="410d9-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="410d9-121">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="410d9-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="410d9-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="410d9-122">E_FAIL</span></span>|<span data-ttu-id="410d9-123">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="410d9-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="410d9-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="410d9-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="410d9-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="410d9-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="410d9-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="410d9-126">Remarks</span></span>  
 <span data-ttu-id="410d9-127">Un puerto de terminación de E/S se crea mediante una llamada a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="410d9-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="410d9-128">CLR llama a `Bind` para enlazar un identificador a ese puerto.</span><span class="sxs-lookup"><span data-stu-id="410d9-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="410d9-129">Cuando se completa una solicitud de E/S, el host debe llamar a la [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="410d9-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="410d9-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="410d9-130">Requirements</span></span>  
 <span data-ttu-id="410d9-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="410d9-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="410d9-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="410d9-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="410d9-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="410d9-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="410d9-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="410d9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="410d9-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="410d9-135">See also</span></span>

- [<span data-ttu-id="410d9-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="410d9-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
