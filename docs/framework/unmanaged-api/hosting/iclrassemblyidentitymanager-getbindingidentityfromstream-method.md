---
description: 'Más información sobre: ICLRAssemblyIdentityManager:: Getbindingidentityfromstream ((método)'
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
ms.openlocfilehash: aed5968a5f5c22a2f5cbea66a350dbe452368325
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716897"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="c77b5-103">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream (Método)</span><span class="sxs-lookup"><span data-stu-id="c77b5-103">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>

<span data-ttu-id="c77b5-104">Obtiene los datos de identidad del ensamblado canónico para el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="c77b5-104">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c77b5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c77b5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c77b5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c77b5-106">Parameters</span></span>  

 `pStream`  
 <span data-ttu-id="c77b5-107">de Secuencia de ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="c77b5-107">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c77b5-108">de Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="c77b5-108">[in] Provided for future extensibility.</span></span> <span data-ttu-id="c77b5-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión actual del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c77b5-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="c77b5-110">enuncia Búfer que contiene los datos de identidad del ensamblado opaco.</span><span class="sxs-lookup"><span data-stu-id="c77b5-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="c77b5-111">[in, out] Tamaño de `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="c77b5-111">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c77b5-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c77b5-112">Return Value</span></span>  
  
|<span data-ttu-id="c77b5-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c77b5-113">HRESULT</span></span>|<span data-ttu-id="c77b5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c77b5-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c77b5-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c77b5-115">S_OK</span></span>|<span data-ttu-id="c77b5-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c77b5-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="c77b5-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c77b5-117">E_INVALIDARG</span></span>|<span data-ttu-id="c77b5-118">El valor de proporcionado `pStream` es NULL.</span><span class="sxs-lookup"><span data-stu-id="c77b5-118">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="c77b5-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="c77b5-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="c77b5-120">El tamaño de `pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="c77b5-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="c77b5-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c77b5-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c77b5-122">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c77b5-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c77b5-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c77b5-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c77b5-124">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c77b5-124">The call timed out.</span></span>|  
|<span data-ttu-id="c77b5-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c77b5-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c77b5-126">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c77b5-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c77b5-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c77b5-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c77b5-128">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c77b5-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c77b5-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c77b5-129">E_FAIL</span></span>|<span data-ttu-id="c77b5-130">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c77b5-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c77b5-131">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c77b5-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c77b5-132">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c77b5-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c77b5-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c77b5-133">Requirements</span></span>  

 <span data-ttu-id="c77b5-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c77b5-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c77b5-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c77b5-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c77b5-136">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c77b5-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c77b5-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c77b5-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c77b5-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c77b5-138">See also</span></span>

- [<span data-ttu-id="c77b5-139">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c77b5-139">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c77b5-140">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c77b5-140">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
