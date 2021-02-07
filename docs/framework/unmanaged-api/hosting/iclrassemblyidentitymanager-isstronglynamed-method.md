---
description: 'Más información sobre: ICLRAssemblyIdentityManager:: Isstronglynamed ((método)'
title: ICLRAssemblyIdentityManager::IsStronglyNamed (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
ms.openlocfilehash: f6f1715513fba56e10b10c14c298d3c553fd4652
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716853"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="3482b-103">ICLRAssemblyIdentityManager::IsStronglyNamed (Método)</span><span class="sxs-lookup"><span data-stu-id="3482b-103">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>

<span data-ttu-id="3482b-104">Obtiene un valor que indica si el ensamblado especificado tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="3482b-104">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3482b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3482b-105">Syntax</span></span>  
  
```cpp  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3482b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3482b-106">Parameters</span></span>  

 `pwzAssemblyIdentity`  
 <span data-ttu-id="3482b-107">de Datos de identidad del ensamblado canónico opaco del ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="3482b-107">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="3482b-108">[out] `true` si el ensamblado al que hace referencia el `pwzAssemblyIdentity` parámetro tiene un nombre seguro; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="3482b-108">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3482b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3482b-109">Return Value</span></span>  
  
|<span data-ttu-id="3482b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3482b-110">HRESULT</span></span>|<span data-ttu-id="3482b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3482b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3482b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3482b-112">S_OK</span></span>|<span data-ttu-id="3482b-113">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3482b-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="3482b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3482b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3482b-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3482b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3482b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3482b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3482b-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3482b-117">The call timed out.</span></span>|  
|<span data-ttu-id="3482b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3482b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3482b-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3482b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3482b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3482b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3482b-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3482b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3482b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3482b-122">E_FAIL</span></span>|<span data-ttu-id="3482b-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3482b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3482b-124">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3482b-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3482b-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3482b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3482b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3482b-126">Requirements</span></span>  

 <span data-ttu-id="3482b-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3482b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3482b-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3482b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3482b-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3482b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3482b-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3482b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3482b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="3482b-131">See also</span></span>

- [<span data-ttu-id="3482b-132">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3482b-132">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
