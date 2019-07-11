---
title: IHostCrst::TryEnter (Método)
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0b4074d9dab8ad46468930373ad44b0c72bd690
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763739"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="63f95-102">IHostCrst::TryEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="63f95-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="63f95-103">Intenta entrar en la sección crítica representada por el actual [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="63f95-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63f95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63f95-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63f95-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63f95-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="63f95-106">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que indica qué acción debe realizar el host si la operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="63f95-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="63f95-107">[out] `true` si la sección crítica puede ser especificado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="63f95-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63f95-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63f95-108">Return Value</span></span>  
  
|<span data-ttu-id="63f95-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63f95-109">HRESULT</span></span>|<span data-ttu-id="63f95-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="63f95-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63f95-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="63f95-111">S_OK</span></span>|<span data-ttu-id="63f95-112">`TryEnter` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="63f95-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="63f95-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63f95-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63f95-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="63f95-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63f95-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63f95-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63f95-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="63f95-116">The call timed out.</span></span>|  
|<span data-ttu-id="63f95-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63f95-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63f95-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="63f95-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63f95-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63f95-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63f95-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="63f95-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63f95-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63f95-121">E_FAIL</span></span>|<span data-ttu-id="63f95-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="63f95-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63f95-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="63f95-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63f95-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="63f95-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63f95-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63f95-125">Remarks</span></span>  
 <span data-ttu-id="63f95-126">`TryEnter` devuelve inmediatamente e indica si el subproceso que realiza la llamada entrado en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="63f95-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="63f95-127">Este método refleja el Win32 `TryEnterCriticalSection` función.</span><span class="sxs-lookup"><span data-stu-id="63f95-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63f95-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63f95-128">Requirements</span></span>  
 <span data-ttu-id="63f95-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63f95-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63f95-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63f95-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63f95-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63f95-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63f95-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63f95-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f95-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="63f95-133">See also</span></span>

- [<span data-ttu-id="63f95-134">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="63f95-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="63f95-135">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="63f95-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="63f95-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="63f95-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
