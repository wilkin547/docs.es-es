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
ms.openlocfilehash: 28fdd5340aee0fcd9875dd983c8c7649b5491c04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674715"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="d45eb-102">ICLRControl::SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="d45eb-102">ICLRControl::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="d45eb-103">Establece un tipo derivado de <xref:System.AppDomainManager> como el tipo para los administradores de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d45eb-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d45eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d45eb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d45eb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d45eb-105">Parameters</span></span>  

 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="d45eb-106">de Nombre del ensamblado en el que se implementa el tipo solicitado derivado de <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="d45eb-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="d45eb-107">de Nombre del tipo implementado en el `pwzAppDomainManagerAssembly` parámetro que implementa las funciones de <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="d45eb-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d45eb-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d45eb-108">Return Value</span></span>  
  
|<span data-ttu-id="d45eb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d45eb-109">HRESULT</span></span>|<span data-ttu-id="d45eb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d45eb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d45eb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d45eb-111">S_OK</span></span>|<span data-ttu-id="d45eb-112">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d45eb-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="d45eb-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d45eb-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d45eb-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d45eb-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d45eb-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d45eb-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d45eb-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d45eb-116">The call timed out.</span></span>|  
|<span data-ttu-id="d45eb-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d45eb-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d45eb-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d45eb-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d45eb-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d45eb-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d45eb-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="d45eb-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d45eb-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d45eb-121">E_FAIL</span></span>|<span data-ttu-id="d45eb-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="d45eb-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d45eb-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d45eb-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d45eb-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d45eb-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d45eb-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d45eb-125">Requirements</span></span>  

 <span data-ttu-id="d45eb-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d45eb-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d45eb-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d45eb-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d45eb-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d45eb-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d45eb-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d45eb-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d45eb-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d45eb-130">See also</span></span>

- [<span data-ttu-id="d45eb-131">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d45eb-131">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="d45eb-132">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d45eb-132">IHostControl Interface</span></span>](ihostcontrol-interface.md)
