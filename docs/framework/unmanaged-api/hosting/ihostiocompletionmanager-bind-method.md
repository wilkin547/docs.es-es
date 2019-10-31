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
ms.openlocfilehash: 84fc99f6a5feb7ec73ee16942ba2794fc082dc89
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133903"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="19ddb-102">IHostIoCompletionManager::Bind (Método)</span><span class="sxs-lookup"><span data-stu-id="19ddb-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="19ddb-103">Enlaza el identificador especificado a un puerto de finalización de e/s creado por una llamada anterior a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="19ddb-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ddb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19ddb-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19ddb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19ddb-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="19ddb-106">de Puerto de finalización de e/s al que se va a enlazar `hHandle`.</span><span class="sxs-lookup"><span data-stu-id="19ddb-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="19ddb-107">Si el valor de `hPort` es null, `hHandle` se enlaza al puerto de finalización de e/s predeterminado.</span><span class="sxs-lookup"><span data-stu-id="19ddb-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="19ddb-108">de Identificador del sistema operativo que se va a enlazar a `hPort`.</span><span class="sxs-lookup"><span data-stu-id="19ddb-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19ddb-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="19ddb-109">Return Value</span></span>  
  
|<span data-ttu-id="19ddb-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19ddb-110">HRESULT</span></span>|<span data-ttu-id="19ddb-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="19ddb-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19ddb-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="19ddb-112">S_OK</span></span>|<span data-ttu-id="19ddb-113">`Bind` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="19ddb-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="19ddb-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19ddb-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19ddb-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="19ddb-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19ddb-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19ddb-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19ddb-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="19ddb-117">The call timed out.</span></span>|  
|<span data-ttu-id="19ddb-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19ddb-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19ddb-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="19ddb-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19ddb-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19ddb-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19ddb-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="19ddb-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19ddb-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19ddb-122">E_FAIL</span></span>|<span data-ttu-id="19ddb-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="19ddb-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19ddb-124">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="19ddb-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19ddb-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="19ddb-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19ddb-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19ddb-126">Remarks</span></span>  
 <span data-ttu-id="19ddb-127">Se crea un puerto de finalización de e/s mediante una llamada a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="19ddb-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="19ddb-128">CLR llama `Bind` para enlazar un identificador a ese puerto.</span><span class="sxs-lookup"><span data-stu-id="19ddb-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19ddb-129">Cuando se completa una solicitud de e/s, el host debe llamar al método [ICLRIoCompletionManager:: alcomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="19ddb-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19ddb-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19ddb-130">Requirements</span></span>  
 <span data-ttu-id="19ddb-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19ddb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19ddb-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="19ddb-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19ddb-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="19ddb-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19ddb-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19ddb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ddb-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="19ddb-135">See also</span></span>

- [<span data-ttu-id="19ddb-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="19ddb-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
