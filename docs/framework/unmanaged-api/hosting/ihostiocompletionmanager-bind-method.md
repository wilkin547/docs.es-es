---
description: 'Más información sobre: IHostIoCompletionManager:: BIND (método)'
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
ms.openlocfilehash: 2105bf06c23f70588d0c1bc0cd849b8e810d121e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784865"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="6b08b-103">IHostIoCompletionManager::Bind (Método)</span><span class="sxs-lookup"><span data-stu-id="6b08b-103">IHostIoCompletionManager::Bind Method</span></span>

<span data-ttu-id="6b08b-104">Enlaza el identificador especificado a un puerto de finalización de e/s creado por una llamada anterior a [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="6b08b-104">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b08b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b08b-105">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b08b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b08b-106">Parameters</span></span>  

 `hPort`  
 <span data-ttu-id="6b08b-107">de Puerto de finalización de e/s al que se va a enlazar `hHandle` .</span><span class="sxs-lookup"><span data-stu-id="6b08b-107">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="6b08b-108">Si el valor de `hPort` es null, `hHandle` se enlaza al puerto de finalización de e/s predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6b08b-108">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="6b08b-109">de Identificador del sistema operativo con el que se va a enlazar `hPort` .</span><span class="sxs-lookup"><span data-stu-id="6b08b-109">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b08b-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6b08b-110">Return Value</span></span>  
  
|<span data-ttu-id="6b08b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b08b-111">HRESULT</span></span>|<span data-ttu-id="6b08b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b08b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b08b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b08b-113">S_OK</span></span>|<span data-ttu-id="6b08b-114">`Bind` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6b08b-114">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="6b08b-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6b08b-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6b08b-116">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6b08b-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6b08b-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6b08b-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6b08b-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6b08b-118">The call timed out.</span></span>|  
|<span data-ttu-id="6b08b-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b08b-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6b08b-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6b08b-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6b08b-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6b08b-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6b08b-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="6b08b-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6b08b-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6b08b-123">E_FAIL</span></span>|<span data-ttu-id="6b08b-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6b08b-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6b08b-125">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6b08b-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6b08b-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6b08b-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b08b-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6b08b-127">Remarks</span></span>  

 <span data-ttu-id="6b08b-128">Se crea un puerto de finalización de e/s mediante una llamada a `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="6b08b-128">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="6b08b-129">CLR llama `Bind` a para enlazar un identificador a ese puerto.</span><span class="sxs-lookup"><span data-stu-id="6b08b-129">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b08b-130">Cuando se completa una solicitud de e/s, el host debe llamar al método [ICLRIoCompletionManager:: alcomplete](iclriocompletionmanager-oncomplete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6b08b-130">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b08b-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b08b-131">Requirements</span></span>  

 <span data-ttu-id="6b08b-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b08b-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b08b-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6b08b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b08b-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b08b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b08b-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b08b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b08b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b08b-136">See also</span></span>

- [<span data-ttu-id="6b08b-137">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b08b-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
