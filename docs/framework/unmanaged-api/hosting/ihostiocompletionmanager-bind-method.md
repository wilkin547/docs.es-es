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
ms.openlocfilehash: 89a30cf4fa95df85e3650459e356a6a82b19bcd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439832"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="b956a-102">IHostIoCompletionManager::Bind (Método)</span><span class="sxs-lookup"><span data-stu-id="b956a-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="b956a-103">Enlaza el identificador especificado con un puerto de finalización de E/S que se ha creado por una llamada anterior a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="b956a-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b956a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b956a-104">Syntax</span></span>  
  
```  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b956a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b956a-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="b956a-106">[in] El puerto de terminación de E/S que se va a enlazar `hHandle`.</span><span class="sxs-lookup"><span data-stu-id="b956a-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="b956a-107">Si el valor de `hPort` es null, `hHandle` está enlazado al puerto de finalización de E/S predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b956a-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="b956a-108">[in] El identificador del sistema operativo para enlazar a `hPort`.</span><span class="sxs-lookup"><span data-stu-id="b956a-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b956a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b956a-109">Return Value</span></span>  
  
|<span data-ttu-id="b956a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b956a-110">HRESULT</span></span>|<span data-ttu-id="b956a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b956a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b956a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b956a-112">S_OK</span></span>|<span data-ttu-id="b956a-113">`Bind` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b956a-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="b956a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b956a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b956a-115">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b956a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b956a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b956a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b956a-117">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b956a-117">The call timed out.</span></span>|  
|<span data-ttu-id="b956a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b956a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b956a-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b956a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b956a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b956a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b956a-121">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b956a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b956a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b956a-122">E_FAIL</span></span>|<span data-ttu-id="b956a-123">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b956a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b956a-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b956a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b956a-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b956a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b956a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b956a-126">Remarks</span></span>  
 <span data-ttu-id="b956a-127">Un puerto de finalización de E/S se crea mediante una llamada a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="b956a-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="b956a-128">CLR llama `Bind` para enlazar un identificador a ese puerto.</span><span class="sxs-lookup"><span data-stu-id="b956a-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b956a-129">Cuando se completa una solicitud de E/S, el host debe llamar a la [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b956a-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b956a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b956a-130">Requirements</span></span>  
 <span data-ttu-id="b956a-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b956a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b956a-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b956a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b956a-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b956a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b956a-134">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b956a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b956a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b956a-135">See Also</span></span>  
 [<span data-ttu-id="b956a-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b956a-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
