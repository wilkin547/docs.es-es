---
description: 'Más información acerca de: ICLRReferenceAssemblyEnum:: get (método)'
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
ms.openlocfilehash: ea4e71631a9ebb381f721b78f17507603891a032
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637305"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="072f5-103">ICLRReferenceAssemblyEnum::Get (Método)</span><span class="sxs-lookup"><span data-stu-id="072f5-103">ICLRReferenceAssemblyEnum::Get Method</span></span>

<span data-ttu-id="072f5-104">Obtiene la identidad del ensamblado en el índice proporcionado.</span><span class="sxs-lookup"><span data-stu-id="072f5-104">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="072f5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="072f5-105">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="072f5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="072f5-106">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="072f5-107">de Índice de base cero de la identidad del ensamblado que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="072f5-107">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="072f5-108">enuncia Búfer que contiene los datos de identidad del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="072f5-108">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="072f5-109">[in, out] Tamaño del `pwzBuffer` búfer.</span><span class="sxs-lookup"><span data-stu-id="072f5-109">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="072f5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="072f5-110">Return Value</span></span>  
  
|<span data-ttu-id="072f5-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="072f5-111">HRESULT</span></span>|<span data-ttu-id="072f5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="072f5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="072f5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="072f5-113">S_OK</span></span>|<span data-ttu-id="072f5-114">`Get` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="072f5-114">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="072f5-115">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="072f5-115">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="072f5-116">`pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="072f5-116">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="072f5-117">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="072f5-117">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="072f5-118">La enumeración no contiene más elementos.</span><span class="sxs-lookup"><span data-stu-id="072f5-118">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="072f5-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="072f5-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="072f5-120">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="072f5-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="072f5-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="072f5-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="072f5-122">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="072f5-122">The call timed out.</span></span>|  
|<span data-ttu-id="072f5-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="072f5-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="072f5-124">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="072f5-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="072f5-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="072f5-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="072f5-126">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="072f5-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="072f5-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="072f5-127">E_FAIL</span></span>|<span data-ttu-id="072f5-128">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="072f5-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="072f5-129">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="072f5-129">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="072f5-130">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="072f5-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="072f5-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="072f5-131">Remarks</span></span>  

 <span data-ttu-id="072f5-132">`Get` normalmente se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="072f5-132">`Get` is typically called twice.</span></span> <span data-ttu-id="072f5-133">La primera llamada proporciona un valor null para `pwzBuffer` , y establece `pcchBufferSize` en el tamaño adecuado para `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="072f5-133">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="072f5-134">La segunda llamada proporciona un tamaño adecuado `pwzBuffer` y contiene los datos de identidad del ensamblado canónico al finalizar.</span><span class="sxs-lookup"><span data-stu-id="072f5-134">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="072f5-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="072f5-135">Requirements</span></span>  

 <span data-ttu-id="072f5-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="072f5-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="072f5-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="072f5-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="072f5-138">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="072f5-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="072f5-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="072f5-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072f5-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="072f5-140">See also</span></span>

- [<span data-ttu-id="072f5-141">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="072f5-141">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="072f5-142">ICLRReferenceAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="072f5-142">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
