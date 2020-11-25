---
title: IHostIoCompletionManager::CreateIoCompletionPort (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
ms.openlocfilehash: 0c74e073d55ab7dc98620052a0cfd68c294f7a1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724278"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="87387-102">IHostIoCompletionManager::CreateIoCompletionPort (Método)</span><span class="sxs-lookup"><span data-stu-id="87387-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>

<span data-ttu-id="87387-103">Solicita que el host cree un nuevo puerto de finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="87387-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87387-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87387-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87387-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87387-105">Parameters</span></span>  

 `phPort`  
 <span data-ttu-id="87387-106">enuncia Un puntero a un identificador del puerto de finalización de e/s recién creado o 0 (cero) si no se pudo crear el puerto.</span><span class="sxs-lookup"><span data-stu-id="87387-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87387-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="87387-107">Return Value</span></span>  
  
|<span data-ttu-id="87387-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87387-108">HRESULT</span></span>|<span data-ttu-id="87387-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="87387-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87387-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="87387-110">S_OK</span></span>|<span data-ttu-id="87387-111">`CreateIoCompletionPort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="87387-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="87387-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87387-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87387-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="87387-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87387-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87387-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87387-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="87387-115">The call timed out.</span></span>|  
|<span data-ttu-id="87387-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87387-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87387-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="87387-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87387-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87387-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87387-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="87387-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87387-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87387-120">E_FAIL</span></span>|<span data-ttu-id="87387-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="87387-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87387-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="87387-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87387-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="87387-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87387-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="87387-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="87387-125">No hay suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="87387-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87387-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87387-126">Remarks</span></span>  

 <span data-ttu-id="87387-127">CLR llama al `CreateIoCompletionPort` método para solicitar que el host cree un nuevo puerto de finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="87387-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="87387-128">Enlaza las operaciones de e/s a este puerto a través de una llamada al método [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="87387-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="87387-129">El host devuelve el estado a CLR llamando a [ICLRIoCompletionManager:: Alcompletate](iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="87387-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87387-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87387-130">Requirements</span></span>  

 <span data-ttu-id="87387-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87387-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87387-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="87387-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87387-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87387-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87387-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87387-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87387-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87387-135">See also</span></span>

- [<span data-ttu-id="87387-136">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87387-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="87387-137">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87387-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
