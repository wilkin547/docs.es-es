---
title: IHostCrst::Enter (Método)
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
ms.openlocfilehash: 79afaac4dce1c4baa9802d81af90c425f5de7a08
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804919"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="21942-102">IHostCrst::Enter (Método)</span><span class="sxs-lookup"><span data-stu-id="21942-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="21942-103">Entra en la sección crítica que representa la instancia de [IHostCrst](ihostcrst-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="21942-103">Enters the critical section that is represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21942-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21942-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21942-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21942-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="21942-106">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) , que indica qué acción debe realizar el host si se bloquea la operación.</span><span class="sxs-lookup"><span data-stu-id="21942-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21942-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="21942-107">Return Value</span></span>  
  
|<span data-ttu-id="21942-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21942-108">HRESULT</span></span>|<span data-ttu-id="21942-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="21942-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="21942-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="21942-110">S_OK</span></span>|<span data-ttu-id="21942-111">`Enter`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="21942-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="21942-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="21942-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="21942-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="21942-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="21942-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="21942-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="21942-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="21942-115">The call timed out.</span></span>|  
|<span data-ttu-id="21942-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="21942-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="21942-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="21942-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="21942-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="21942-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="21942-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="21942-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="21942-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="21942-120">E_FAIL</span></span>|<span data-ttu-id="21942-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="21942-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="21942-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="21942-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="21942-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="21942-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21942-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="21942-124">Remarks</span></span>  
 <span data-ttu-id="21942-125">`Enter`refleja la función de Win32 `EnterCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="21942-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21942-126">Este método no devuelve ningún resultado hasta que se especifica la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="21942-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21942-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21942-127">Requirements</span></span>  
 <span data-ttu-id="21942-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21942-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21942-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="21942-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21942-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="21942-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21942-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21942-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21942-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21942-132">See also</span></span>

- [<span data-ttu-id="21942-133">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21942-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="21942-134">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21942-134">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="21942-135">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21942-135">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
