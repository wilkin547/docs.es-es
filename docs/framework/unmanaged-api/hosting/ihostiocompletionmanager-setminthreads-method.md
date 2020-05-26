---
title: IHostIoCompletionManager::SetMinThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
ms.openlocfilehash: 29a2fc5652badcc00378192debccba0356f5339e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804653"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="27292-102">IHostIoCompletionManager::SetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="27292-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="27292-103">Establece el número mínimo de subprocesos que el host debe asignar a la finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="27292-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27292-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27292-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27292-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27292-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="27292-106">de Número mínimo de subprocesos de finalización de e/s que debe crear el host.</span><span class="sxs-lookup"><span data-stu-id="27292-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27292-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="27292-107">Return Value</span></span>  
  
|<span data-ttu-id="27292-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27292-108">HRESULT</span></span>|<span data-ttu-id="27292-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="27292-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27292-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="27292-110">S_OK</span></span>|<span data-ttu-id="27292-111">`SetMinThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="27292-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="27292-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27292-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27292-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="27292-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27292-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27292-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27292-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="27292-115">The call timed out.</span></span>|  
|<span data-ttu-id="27292-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27292-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27292-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="27292-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27292-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27292-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27292-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="27292-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27292-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27292-120">E_FAIL</span></span>|<span data-ttu-id="27292-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="27292-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27292-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="27292-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27292-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="27292-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="27292-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="27292-124">E_NOTIMPL</span></span>|<span data-ttu-id="27292-125">El host no proporciona una implementación de `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="27292-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27292-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="27292-126">Remarks</span></span>  
 <span data-ttu-id="27292-127">Un host podría querer controlar de forma exclusiva el número de subprocesos que se pueden asignar para procesar solicitudes de e/s, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="27292-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="27292-128">Por esta razón, no es necesario que el host implemente `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="27292-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="27292-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="27292-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27292-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27292-130">Requirements</span></span>  
 <span data-ttu-id="27292-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27292-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27292-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="27292-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27292-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="27292-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27292-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27292-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27292-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27292-135">See also</span></span>

- [<span data-ttu-id="27292-136">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27292-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="27292-137">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="27292-137">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="27292-138">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27292-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
