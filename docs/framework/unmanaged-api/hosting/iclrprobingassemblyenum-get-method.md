---
title: ICLRProbingAssemblyEnum::Get (Método)
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 909e18fe9086fa954ffc389ffe1c6fe49217d2f5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492457"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="fe5fe-102">ICLRProbingAssemblyEnum::Get (Método)</span><span class="sxs-lookup"><span data-stu-id="fe5fe-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="fe5fe-103">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe5fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe5fe-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe5fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe5fe-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="fe5fe-106">[in] Índice de base cero de la identidad del ensamblado para devolver.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="fe5fe-107">[out] Un búfer que contiene los datos de identidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="fe5fe-108">[in, out] El tamaño de la `pwzBuffer` búfer.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe5fe-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fe5fe-109">Return Value</span></span>  
  
|<span data-ttu-id="fe5fe-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe5fe-110">HRESULT</span></span>|<span data-ttu-id="fe5fe-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe5fe-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe5fe-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe5fe-112">S_OK</span></span>|<span data-ttu-id="fe5fe-113">`Get` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="fe5fe-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="fe5fe-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="fe5fe-115">`pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="fe5fe-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="fe5fe-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="fe5fe-117">La enumeración no contiene ningún elemento más.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="fe5fe-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe5fe-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe5fe-119">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe5fe-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe5fe-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe5fe-121">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-121">The call timed out.</span></span>|  
|<span data-ttu-id="fe5fe-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe5fe-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe5fe-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe5fe-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe5fe-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe5fe-125">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe5fe-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe5fe-126">E_FAIL</span></span>|<span data-ttu-id="fe5fe-127">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe5fe-128">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe5fe-129">Las llamadas subsiguientes a cualquier método de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe5fe-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe5fe-130">Remarks</span></span>  
 <span data-ttu-id="fe5fe-131">La identidad en el índice 0 es la identidad específica para la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="fe5fe-132">La identidad en el índice 1 es el ensamblado de arquitectura neutral para el lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="fe5fe-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="fe5fe-133">La identidad en el índice 2 no contiene ninguna información de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="fe5fe-134">`Get` Normalmente, se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-134">`Get` is typically called twice.</span></span> <span data-ttu-id="fe5fe-135">La primera llamada proporciona un valor null para `pwzBuffer`y establece `pcchBufferSize` en el tamaño adecuado para `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="fe5fe-136">La segunda llamada proporciona un tamaño adecuado `pwzBuffer`y contiene los datos de identidad de ensamblado canónico tras la finalización.</span><span class="sxs-lookup"><span data-stu-id="fe5fe-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe5fe-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe5fe-137">Requirements</span></span>  
 <span data-ttu-id="fe5fe-138">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe5fe-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe5fe-139">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fe5fe-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe5fe-140">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe5fe-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe5fe-141">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe5fe-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5fe-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe5fe-142">See also</span></span>
- [<span data-ttu-id="fe5fe-143">ICLRProbingAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5fe-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="fe5fe-144">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe5fe-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
