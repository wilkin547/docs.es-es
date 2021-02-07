---
description: 'Más información acerca de: ICLRProbingAssemblyEnum:: get (método)'
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
ms.openlocfilehash: 77fb93b30a3b9b01b32fef9af661c84f484ef758
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716528"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="bee61-103">ICLRProbingAssemblyEnum::Get (Método)</span><span class="sxs-lookup"><span data-stu-id="bee61-103">ICLRProbingAssemblyEnum::Get Method</span></span>

<span data-ttu-id="bee61-104">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="bee61-104">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bee61-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bee61-105">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bee61-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bee61-106">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="bee61-107">de Índice de base cero de la identidad del ensamblado que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="bee61-107">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="bee61-108">enuncia Búfer que contiene los datos de identidad del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bee61-108">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="bee61-109">[in, out] Tamaño del `pwzBuffer` búfer.</span><span class="sxs-lookup"><span data-stu-id="bee61-109">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bee61-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bee61-110">Return Value</span></span>  
  
|<span data-ttu-id="bee61-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bee61-111">HRESULT</span></span>|<span data-ttu-id="bee61-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bee61-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bee61-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="bee61-113">S_OK</span></span>|<span data-ttu-id="bee61-114">`Get` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bee61-114">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="bee61-115">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="bee61-115">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="bee61-116">`pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="bee61-116">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="bee61-117">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="bee61-117">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="bee61-118">La enumeración no contiene más elementos.</span><span class="sxs-lookup"><span data-stu-id="bee61-118">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="bee61-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bee61-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bee61-120">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bee61-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bee61-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bee61-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bee61-122">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bee61-122">The call timed out.</span></span>|  
|<span data-ttu-id="bee61-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bee61-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bee61-124">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bee61-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bee61-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bee61-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bee61-126">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="bee61-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bee61-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bee61-127">E_FAIL</span></span>|<span data-ttu-id="bee61-128">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="bee61-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bee61-129">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bee61-129">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bee61-130">Las llamadas subsiguientes a cualquier método de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bee61-130">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bee61-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bee61-131">Remarks</span></span>  

 <span data-ttu-id="bee61-132">La identidad del índice 0 es la identidad específica de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="bee61-132">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="bee61-133">La identidad del índice 1 es el ensamblado independiente de la arquitectura para el lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="bee61-133">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="bee61-134">La identidad del índice 2 no contiene información de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="bee61-134">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="bee61-135">`Get` normalmente se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="bee61-135">`Get` is typically called twice.</span></span> <span data-ttu-id="bee61-136">La primera llamada proporciona un valor null para `pwzBuffer` , y establece `pcchBufferSize` en el tamaño adecuado para `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="bee61-136">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="bee61-137">La segunda llamada proporciona un tamaño adecuado `pwzBuffer` y contiene los datos de identidad del ensamblado canónico al finalizar.</span><span class="sxs-lookup"><span data-stu-id="bee61-137">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bee61-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bee61-138">Requirements</span></span>  

 <span data-ttu-id="bee61-139">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bee61-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bee61-140">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bee61-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bee61-141">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bee61-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bee61-142">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bee61-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee61-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="bee61-143">See also</span></span>

- [<span data-ttu-id="bee61-144">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bee61-144">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="bee61-145">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bee61-145">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
