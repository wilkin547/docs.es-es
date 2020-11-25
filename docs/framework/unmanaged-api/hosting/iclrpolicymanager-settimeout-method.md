---
title: ICLRPolicyManager::SetTimeout (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
ms.openlocfilehash: 459c5bc0699487b62d5dcf76f1044faf53ebab8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732468"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="ea436-102">ICLRPolicyManager::SetTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="ea436-102">ICLRPolicyManager::SetTimeout Method</span></span>

<span data-ttu-id="ea436-103">Establece un valor de tiempo de espera para la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="ea436-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea436-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea436-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea436-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea436-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="ea436-106">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica la operación de Common Language Runtime (CLR) para la que se va a establecer un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ea436-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="ea436-107">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ea436-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="ea436-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="ea436-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="ea436-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="ea436-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="ea436-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ea436-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="ea436-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ea436-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="ea436-112">de Nuevo valor de tiempo de espera, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="ea436-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="ea436-113">Un valor de Infinite hace que la operación nunca agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ea436-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea436-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ea436-114">Return Value</span></span>  
  
|<span data-ttu-id="ea436-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea436-115">HRESULT</span></span>|<span data-ttu-id="ea436-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea436-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea436-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea436-117">S_OK</span></span>|<span data-ttu-id="ea436-118">`SetTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ea436-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="ea436-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ea436-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ea436-120">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ea436-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ea436-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ea436-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ea436-122">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ea436-122">The call timed out.</span></span>|  
|<span data-ttu-id="ea436-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ea436-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ea436-124">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ea436-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ea436-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ea436-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ea436-126">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ea436-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ea436-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ea436-127">E_FAIL</span></span>|<span data-ttu-id="ea436-128">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ea436-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ea436-129">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ea436-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ea436-130">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ea436-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ea436-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ea436-131">E_INVALIDARG</span></span>|<span data-ttu-id="ea436-132">No se puede establecer un tiempo de espera para el especificado `operation` o se proporcionó un valor no válido para `operation` .</span><span class="sxs-lookup"><span data-stu-id="ea436-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea436-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea436-133">Requirements</span></span>  

 <span data-ttu-id="ea436-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea436-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea436-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ea436-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea436-136">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea436-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea436-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea436-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea436-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea436-138">See also</span></span>

- [<span data-ttu-id="ea436-139">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ea436-139">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="ea436-140">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea436-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ea436-141">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea436-141">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
