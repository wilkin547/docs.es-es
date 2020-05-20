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
ms.openlocfilehash: 5afa7b37b804b6a11a894e0e6c7708c7787a20ae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703368"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="62f6f-102">ICLRReferenceAssemblyEnum::Get (Método)</span><span class="sxs-lookup"><span data-stu-id="62f6f-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="62f6f-103">Obtiene la identidad del ensamblado en el índice proporcionado.</span><span class="sxs-lookup"><span data-stu-id="62f6f-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62f6f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62f6f-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62f6f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62f6f-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="62f6f-106">de Índice de base cero de la identidad del ensamblado que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="62f6f-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="62f6f-107">enuncia Búfer que contiene los datos de identidad del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="62f6f-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="62f6f-108">[in, out] Tamaño del `pwzBuffer` búfer.</span><span class="sxs-lookup"><span data-stu-id="62f6f-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62f6f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="62f6f-109">Return Value</span></span>  
  
|<span data-ttu-id="62f6f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62f6f-110">HRESULT</span></span>|<span data-ttu-id="62f6f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="62f6f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62f6f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="62f6f-112">S_OK</span></span>|<span data-ttu-id="62f6f-113">`Get`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="62f6f-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="62f6f-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="62f6f-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="62f6f-115">`pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="62f6f-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="62f6f-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="62f6f-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="62f6f-117">La enumeración no contiene más elementos.</span><span class="sxs-lookup"><span data-stu-id="62f6f-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="62f6f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62f6f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62f6f-119">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="62f6f-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62f6f-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62f6f-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62f6f-121">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="62f6f-121">The call timed out.</span></span>|  
|<span data-ttu-id="62f6f-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62f6f-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62f6f-123">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="62f6f-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62f6f-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62f6f-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62f6f-125">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="62f6f-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62f6f-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62f6f-126">E_FAIL</span></span>|<span data-ttu-id="62f6f-127">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="62f6f-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62f6f-128">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="62f6f-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62f6f-129">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="62f6f-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62f6f-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62f6f-130">Remarks</span></span>  
 <span data-ttu-id="62f6f-131">`Get`normalmente se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="62f6f-131">`Get` is typically called twice.</span></span> <span data-ttu-id="62f6f-132">La primera llamada proporciona un valor null para `pwzBuffer` , y establece `pcchBufferSize` en el tamaño adecuado para `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="62f6f-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="62f6f-133">La segunda llamada proporciona un tamaño adecuado `pwzBuffer` y contiene los datos de identidad del ensamblado canónico al finalizar.</span><span class="sxs-lookup"><span data-stu-id="62f6f-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62f6f-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62f6f-134">Requirements</span></span>  
 <span data-ttu-id="62f6f-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62f6f-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62f6f-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="62f6f-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62f6f-137">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62f6f-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62f6f-138">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62f6f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f6f-139">Consulta también</span><span class="sxs-lookup"><span data-stu-id="62f6f-139">See also</span></span>

- [<span data-ttu-id="62f6f-140">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62f6f-140">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="62f6f-141">ICLRReferenceAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62f6f-141">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
