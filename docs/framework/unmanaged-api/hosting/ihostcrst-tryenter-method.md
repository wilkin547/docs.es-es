---
description: 'Más información acerca de: IHostCrst:: TryEnter (método)'
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
ms.openlocfilehash: 59c632b7c9edd422e2ceee1e0526a7bb077759a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708741"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="48005-103">IHostCrst::TryEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="48005-103">IHostCrst::TryEnter Method</span></span>

<span data-ttu-id="48005-104">Intenta entrar en la sección crítica representada por la instancia de [IHostCrst](ihostcrst-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="48005-104">Attempts to enter the critical section represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48005-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48005-105">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48005-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48005-106">Parameters</span></span>  

 `option`  
 <span data-ttu-id="48005-107">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) , que indica qué acción debe realizar el host si se bloquea la operación.</span><span class="sxs-lookup"><span data-stu-id="48005-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="48005-108">[out] `true` Si se puede especificar la sección crítica; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="48005-108">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48005-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="48005-109">Return Value</span></span>  
  
|<span data-ttu-id="48005-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48005-110">HRESULT</span></span>|<span data-ttu-id="48005-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="48005-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48005-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="48005-112">S_OK</span></span>|<span data-ttu-id="48005-113">`TryEnter` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="48005-113">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="48005-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48005-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48005-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="48005-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48005-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48005-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48005-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="48005-117">The call timed out.</span></span>|  
|<span data-ttu-id="48005-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48005-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48005-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="48005-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48005-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48005-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48005-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="48005-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48005-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48005-122">E_FAIL</span></span>|<span data-ttu-id="48005-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="48005-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48005-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="48005-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48005-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="48005-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48005-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48005-126">Remarks</span></span>  

 <span data-ttu-id="48005-127">`TryEnter` devuelve inmediatamente e indica si el subproceso que realiza la llamada entró en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="48005-127">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="48005-128">Este método refleja la `TryEnterCriticalSection` función Wind32.</span><span class="sxs-lookup"><span data-stu-id="48005-128">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48005-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48005-129">Requirements</span></span>  

 <span data-ttu-id="48005-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48005-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48005-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="48005-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48005-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48005-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48005-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48005-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48005-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="48005-134">See also</span></span>

- [<span data-ttu-id="48005-135">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="48005-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="48005-136">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="48005-136">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="48005-137">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="48005-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
