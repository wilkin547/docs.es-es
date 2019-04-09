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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194479"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="518c0-102">ICLRReferenceAssemblyEnum::Get (Método)</span><span class="sxs-lookup"><span data-stu-id="518c0-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="518c0-103">Obtiene la identidad del ensamblado en el índice proporcionado.</span><span class="sxs-lookup"><span data-stu-id="518c0-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="518c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="518c0-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="518c0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="518c0-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="518c0-106">[in] Índice de base cero de la identidad del ensamblado para devolver.</span><span class="sxs-lookup"><span data-stu-id="518c0-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="518c0-107">[out] Un búfer que contiene los datos de identidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="518c0-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="518c0-108">[in, out] El tamaño de la `pwzBuffer` búfer.</span><span class="sxs-lookup"><span data-stu-id="518c0-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="518c0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="518c0-109">Return Value</span></span>  
  
|<span data-ttu-id="518c0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="518c0-110">HRESULT</span></span>|<span data-ttu-id="518c0-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="518c0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="518c0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="518c0-112">S_OK</span></span>|`Get` <span data-ttu-id="518c0-113">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="518c0-113">returned successfully.</span></span>|  
|<span data-ttu-id="518c0-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="518c0-114">ERROR_INSUFFICIENT_BUFFER</span></span>|`pwzBuffer` <span data-ttu-id="518c0-115">es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="518c0-115">is too small.</span></span>|  
|<span data-ttu-id="518c0-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="518c0-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="518c0-117">La enumeración no contiene ningún elemento más.</span><span class="sxs-lookup"><span data-stu-id="518c0-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="518c0-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="518c0-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="518c0-119">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="518c0-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="518c0-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="518c0-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="518c0-121">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="518c0-121">The call timed out.</span></span>|  
|<span data-ttu-id="518c0-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="518c0-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="518c0-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="518c0-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="518c0-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="518c0-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="518c0-125">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="518c0-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="518c0-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="518c0-126">E_FAIL</span></span>|<span data-ttu-id="518c0-127">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="518c0-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="518c0-128">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="518c0-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="518c0-129">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="518c0-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="518c0-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="518c0-130">Remarks</span></span>  
 `Get` <span data-ttu-id="518c0-131">Normalmente, se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="518c0-131">is typically called twice.</span></span> <span data-ttu-id="518c0-132">La primera llamada proporciona un valor null para `pwzBuffer`y establece `pcchBufferSize` en el tamaño adecuado para `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="518c0-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="518c0-133">La segunda llamada proporciona un tamaño adecuado `pwzBuffer`y contiene los datos de identidad de ensamblado canónico tras la finalización.</span><span class="sxs-lookup"><span data-stu-id="518c0-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="518c0-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="518c0-134">Requirements</span></span>  
 <span data-ttu-id="518c0-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="518c0-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="518c0-136">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="518c0-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="518c0-137">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="518c0-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="518c0-138">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="518c0-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="518c0-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="518c0-139">See also</span></span>

- [<span data-ttu-id="518c0-140">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="518c0-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="518c0-141">ICLRReferenceAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="518c0-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
