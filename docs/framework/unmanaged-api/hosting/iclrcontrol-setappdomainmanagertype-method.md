---
description: 'Más información acerca de: ICLRControl:: Setappdomainmanagertype ((método)'
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
ms.openlocfilehash: 20d45a0ab14904c778a6ea821fcd63f85b6b0921
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716671"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="4154b-103">ICLRControl::SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="4154b-103">ICLRControl::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="4154b-104">Establece un tipo derivado de <xref:System.AppDomainManager> como el tipo para los administradores de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4154b-104">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4154b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4154b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4154b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4154b-106">Parameters</span></span>  

 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="4154b-107">de Nombre del ensamblado en el que se implementa el tipo solicitado derivado de <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="4154b-107">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="4154b-108">de Nombre del tipo implementado en el `pwzAppDomainManagerAssembly` parámetro que implementa las funciones de <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="4154b-108">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4154b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4154b-109">Return Value</span></span>  
  
|<span data-ttu-id="4154b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4154b-110">HRESULT</span></span>|<span data-ttu-id="4154b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4154b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4154b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4154b-112">S_OK</span></span>|<span data-ttu-id="4154b-113">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4154b-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="4154b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4154b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4154b-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4154b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4154b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4154b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4154b-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="4154b-117">The call timed out.</span></span>|  
|<span data-ttu-id="4154b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4154b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4154b-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4154b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4154b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4154b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4154b-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="4154b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4154b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4154b-122">E_FAIL</span></span>|<span data-ttu-id="4154b-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="4154b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4154b-124">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4154b-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4154b-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4154b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4154b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4154b-126">Requirements</span></span>  

 <span data-ttu-id="4154b-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4154b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4154b-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4154b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4154b-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4154b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4154b-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4154b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4154b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="4154b-131">See also</span></span>

- [<span data-ttu-id="4154b-132">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4154b-132">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="4154b-133">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4154b-133">IHostControl Interface</span></span>](ihostcontrol-interface.md)
