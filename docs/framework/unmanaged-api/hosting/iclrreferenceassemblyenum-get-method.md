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
ms.openlocfilehash: d8cfb2f18bcceed3a125ac7876122c02d2267698
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436460"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="2e9a9-102">ICLRReferenceAssemblyEnum::Get (Método)</span><span class="sxs-lookup"><span data-stu-id="2e9a9-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="2e9a9-103">Obtiene la identidad del ensamblado en el índice proporcionado.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e9a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e9a9-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e9a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e9a9-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="2e9a9-106">[in] Índice de base cero de la identidad del ensamblado para devolver.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="2e9a9-107">[out] Un búfer que contiene los datos de identidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="2e9a9-108">[entrada, salida] El tamaño de la `pwzBuffer` búfer.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e9a9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2e9a9-109">Return Value</span></span>  
  
|<span data-ttu-id="2e9a9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e9a9-110">HRESULT</span></span>|<span data-ttu-id="2e9a9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e9a9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e9a9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e9a9-112">S_OK</span></span>|<span data-ttu-id="2e9a9-113">`Get` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="2e9a9-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="2e9a9-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="2e9a9-115">`pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="2e9a9-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="2e9a9-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="2e9a9-117">La enumeración no contiene más elementos.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="2e9a9-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e9a9-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e9a9-119">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e9a9-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e9a9-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e9a9-121">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-121">The call timed out.</span></span>|  
|<span data-ttu-id="2e9a9-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e9a9-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e9a9-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e9a9-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e9a9-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e9a9-125">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e9a9-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e9a9-126">E_FAIL</span></span>|<span data-ttu-id="2e9a9-127">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e9a9-128">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e9a9-129">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e9a9-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e9a9-130">Remarks</span></span>  
 <span data-ttu-id="2e9a9-131">`Get` Normalmente se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-131">`Get` is typically called twice.</span></span> <span data-ttu-id="2e9a9-132">La primera llamada proporciona un valor null para `pwzBuffer`y establece `pcchBufferSize` en el tamaño adecuado para `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="2e9a9-133">La segunda llamada proporciona un tamaño adecuado `pwzBuffer`y contiene los datos de identidad de ensamblado canónicos tras la finalización.</span><span class="sxs-lookup"><span data-stu-id="2e9a9-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e9a9-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e9a9-134">Requirements</span></span>  
 <span data-ttu-id="2e9a9-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e9a9-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e9a9-136">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e9a9-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e9a9-137">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e9a9-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e9a9-138">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e9a9-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9a9-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e9a9-139">See Also</span></span>  
 [<span data-ttu-id="2e9a9-140">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e9a9-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="2e9a9-141">ICLRReferenceAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e9a9-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
