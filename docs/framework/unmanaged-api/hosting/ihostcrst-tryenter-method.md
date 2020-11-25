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
ms.openlocfilehash: 02f36068f12bf0a40e5f0ac477803abfb84c72a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729543"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="50254-102">IHostCrst::TryEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="50254-102">IHostCrst::TryEnter Method</span></span>

<span data-ttu-id="50254-103">Intenta entrar en la sección crítica representada por la instancia de [IHostCrst](ihostcrst-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="50254-103">Attempts to enter the critical section represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50254-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50254-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50254-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50254-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="50254-106">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) , que indica qué acción debe realizar el host si se bloquea la operación.</span><span class="sxs-lookup"><span data-stu-id="50254-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="50254-107">[out] `true` Si se puede especificar la sección crítica; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="50254-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50254-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="50254-108">Return Value</span></span>  
  
|<span data-ttu-id="50254-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50254-109">HRESULT</span></span>|<span data-ttu-id="50254-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="50254-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50254-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="50254-111">S_OK</span></span>|<span data-ttu-id="50254-112">`TryEnter` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="50254-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="50254-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50254-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50254-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="50254-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50254-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50254-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50254-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="50254-116">The call timed out.</span></span>|  
|<span data-ttu-id="50254-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50254-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50254-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="50254-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50254-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50254-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50254-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="50254-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50254-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50254-121">E_FAIL</span></span>|<span data-ttu-id="50254-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="50254-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50254-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="50254-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50254-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="50254-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50254-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50254-125">Remarks</span></span>  

 <span data-ttu-id="50254-126">`TryEnter` devuelve inmediatamente e indica si el subproceso que realiza la llamada entró en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="50254-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="50254-127">Este método refleja la `TryEnterCriticalSection` función Wind32.</span><span class="sxs-lookup"><span data-stu-id="50254-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50254-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50254-128">Requirements</span></span>  

 <span data-ttu-id="50254-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50254-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50254-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="50254-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50254-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50254-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50254-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50254-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50254-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50254-133">See also</span></span>

- [<span data-ttu-id="50254-134">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50254-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="50254-135">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50254-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="50254-136">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50254-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
