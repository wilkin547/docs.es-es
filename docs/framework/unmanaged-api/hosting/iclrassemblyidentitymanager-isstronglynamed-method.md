---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1c1b2d8274baf5fd43991979bc65cd2c2299b46
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484698"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="51488-102">ICLRAssemblyIdentityManager::IsStronglyNamed (Método)</span><span class="sxs-lookup"><span data-stu-id="51488-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="51488-103">Obtiene un valor que indica si el ensamblado especificado tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="51488-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51488-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51488-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51488-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51488-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="51488-106">[in] Los datos de identidad de ensamblado canónico opaco del ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="51488-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="51488-107">[out] `true`, si el ensamblado al que hace referencia el `pwzAssemblyIdentity` parámetro está fuertemente con nombre; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="51488-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51488-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="51488-108">Return Value</span></span>  
  
|<span data-ttu-id="51488-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51488-109">HRESULT</span></span>|<span data-ttu-id="51488-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="51488-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51488-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="51488-111">S_OK</span></span>|<span data-ttu-id="51488-112">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="51488-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="51488-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51488-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51488-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="51488-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51488-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51488-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51488-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="51488-116">The call timed out.</span></span>|  
|<span data-ttu-id="51488-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51488-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51488-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="51488-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51488-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51488-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51488-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="51488-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51488-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51488-121">E_FAIL</span></span>|<span data-ttu-id="51488-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="51488-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51488-123">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="51488-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51488-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="51488-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51488-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51488-125">Requirements</span></span>  
 <span data-ttu-id="51488-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51488-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51488-127">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="51488-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51488-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51488-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51488-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51488-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51488-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="51488-130">See also</span></span>
- [<span data-ttu-id="51488-131">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51488-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
