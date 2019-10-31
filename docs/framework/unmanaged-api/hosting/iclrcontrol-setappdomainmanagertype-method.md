---
title: ICLRControl::SetAppDomainManagerType (Método)
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
ms.openlocfilehash: be29a4f83901b8e8fc338c2daa8f5703523402b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126585"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="75eba-102">ICLRControl::SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="75eba-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="75eba-103">Establece un tipo derivado de <xref:System.AppDomainManager> como tipo para los administradores de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75eba-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75eba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75eba-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75eba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75eba-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="75eba-106">de Nombre del ensamblado en el que se implementa el tipo solicitado derivado de <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="75eba-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="75eba-107">de Nombre del tipo implementado en el `pwzAppDomainManagerAssembly` parámetro que implementa las capacidades de <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="75eba-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75eba-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="75eba-108">Return Value</span></span>  
  
|<span data-ttu-id="75eba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75eba-109">HRESULT</span></span>|<span data-ttu-id="75eba-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="75eba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75eba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="75eba-111">S_OK</span></span>|<span data-ttu-id="75eba-112">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="75eba-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="75eba-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="75eba-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="75eba-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="75eba-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="75eba-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="75eba-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="75eba-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="75eba-116">The call timed out.</span></span>|  
|<span data-ttu-id="75eba-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="75eba-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="75eba-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="75eba-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="75eba-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="75eba-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="75eba-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="75eba-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="75eba-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="75eba-121">E_FAIL</span></span>|<span data-ttu-id="75eba-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="75eba-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="75eba-123">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="75eba-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="75eba-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="75eba-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75eba-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75eba-125">Requirements</span></span>  
 <span data-ttu-id="75eba-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75eba-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75eba-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="75eba-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="75eba-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="75eba-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75eba-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75eba-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75eba-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="75eba-130">See also</span></span>

- [<span data-ttu-id="75eba-131">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="75eba-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="75eba-132">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="75eba-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
