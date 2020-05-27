---
title: IHostIoCompletionManager::CloseIoCompletionPort (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
ms.openlocfilehash: 5e2e49b4c993e127a31b54d40f721e0714198780
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804775"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="c8ecb-102">IHostIoCompletionManager::CloseIoCompletionPort (Método)</span><span class="sxs-lookup"><span data-stu-id="c8ecb-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="c8ecb-103">Solicita que el host cierre un puerto que se abrió a través de una llamada anterior a [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="c8ecb-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8ecb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8ecb-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8ecb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8ecb-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="c8ecb-106">de Identificador del puerto que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8ecb-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c8ecb-107">Return Value</span></span>  
  
|<span data-ttu-id="c8ecb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8ecb-108">HRESULT</span></span>|<span data-ttu-id="c8ecb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8ecb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8ecb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8ecb-110">S_OK</span></span>|<span data-ttu-id="c8ecb-111">`CloseIoCompletionPort`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="c8ecb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8ecb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8ecb-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c8ecb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c8ecb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c8ecb-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-115">The call timed out.</span></span>|  
|<span data-ttu-id="c8ecb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c8ecb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c8ecb-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c8ecb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c8ecb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c8ecb-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c8ecb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8ecb-120">E_FAIL</span></span>|<span data-ttu-id="c8ecb-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c8ecb-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c8ecb-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c8ecb-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c8ecb-124">E_INVALIDARG</span></span>|<span data-ttu-id="c8ecb-125">Se pasó un identificador de puerto no válido.</span><span class="sxs-lookup"><span data-stu-id="c8ecb-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8ecb-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c8ecb-126">Remarks</span></span>  
 <span data-ttu-id="c8ecb-127">`hPort`debe ser un identificador de un puerto creado por una llamada anterior a `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="c8ecb-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8ecb-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8ecb-128">Requirements</span></span>  
 <span data-ttu-id="c8ecb-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8ecb-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8ecb-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c8ecb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8ecb-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c8ecb-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8ecb-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8ecb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ecb-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8ecb-133">See also</span></span>

- [<span data-ttu-id="c8ecb-134">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8ecb-134">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c8ecb-135">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8ecb-135">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
