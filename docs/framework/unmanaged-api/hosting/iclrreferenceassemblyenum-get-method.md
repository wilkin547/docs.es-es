---
title: ICLRReferenceAssemblyEnum::Get (Método)
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31d26ed6249bad8a7e2fbaab01264c1b32e1ff55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638663"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="b2750-102">ICLRReferenceAssemblyEnum::Get (Método)</span><span class="sxs-lookup"><span data-stu-id="b2750-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="b2750-103">Obtiene la identidad del ensamblado en el índice proporcionado.</span><span class="sxs-lookup"><span data-stu-id="b2750-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2750-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2750-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2750-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2750-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="b2750-106">[in] Índice de base cero de la identidad del ensamblado para devolver.</span><span class="sxs-lookup"><span data-stu-id="b2750-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="b2750-107">[out] Un búfer que contiene los datos de identidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b2750-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="b2750-108">[in, out] El tamaño de la `pwzBuffer` búfer.</span><span class="sxs-lookup"><span data-stu-id="b2750-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2750-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2750-109">Return Value</span></span>  
  
|<span data-ttu-id="b2750-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2750-110">HRESULT</span></span>|<span data-ttu-id="b2750-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2750-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2750-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2750-112">S_OK</span></span>|<span data-ttu-id="b2750-113">`Get` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b2750-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="b2750-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b2750-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b2750-115">`pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="b2750-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="b2750-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="b2750-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="b2750-117">La enumeración no contiene ningún elemento más.</span><span class="sxs-lookup"><span data-stu-id="b2750-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="b2750-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2750-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2750-119">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b2750-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2750-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2750-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2750-121">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b2750-121">The call timed out.</span></span>|  
|<span data-ttu-id="b2750-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2750-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2750-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b2750-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2750-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2750-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2750-125">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="b2750-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2750-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2750-126">E_FAIL</span></span>|<span data-ttu-id="b2750-127">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="b2750-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2750-128">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b2750-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2750-129">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2750-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2750-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2750-130">Remarks</span></span>  
 <span data-ttu-id="b2750-131">`Get` Normalmente, se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="b2750-131">`Get` is typically called twice.</span></span> <span data-ttu-id="b2750-132">La primera llamada proporciona un valor null para `pwzBuffer`y establece `pcchBufferSize` en el tamaño adecuado para `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="b2750-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="b2750-133">La segunda llamada proporciona un tamaño adecuado `pwzBuffer`y contiene los datos de identidad de ensamblado canónico tras la finalización.</span><span class="sxs-lookup"><span data-stu-id="b2750-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2750-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2750-134">Requirements</span></span>  
 <span data-ttu-id="b2750-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2750-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2750-136">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2750-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2750-137">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2750-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2750-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2750-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2750-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2750-139">See also</span></span>

- [<span data-ttu-id="b2750-140">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2750-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b2750-141">ICLRReferenceAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2750-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
