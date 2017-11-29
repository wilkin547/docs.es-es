---
title: "IHostAssemblyManager::GetAssemblyStore (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager.GetAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d838ee8383a4e11f5d43c4a3751c4a90503906fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="c1b32-102">IHostAssemblyManager::GetAssemblyStore (Método)</span><span class="sxs-lookup"><span data-stu-id="c1b32-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="c1b32-103">Obtiene un puntero de interfaz a una [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="c1b32-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1b32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1b32-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1b32-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1b32-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="c1b32-106">[out] Un puntero a función para un `IHostAssemblyStore` instancia o null si el host no implementa `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="c1b32-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1b32-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c1b32-107">Return Value</span></span>  
  
|<span data-ttu-id="c1b32-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1b32-108">HRESULT</span></span>|<span data-ttu-id="c1b32-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1b32-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1b32-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1b32-110">S_OK</span></span>|<span data-ttu-id="c1b32-111">`GetAssemblyStore`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1b32-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="c1b32-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c1b32-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c1b32-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1b32-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c1b32-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1b32-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c1b32-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c1b32-115">The call timed out.</span></span>|  
|<span data-ttu-id="c1b32-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c1b32-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c1b32-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c1b32-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c1b32-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c1b32-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c1b32-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="c1b32-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c1b32-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c1b32-120">E_FAIL</span></span>|<span data-ttu-id="c1b32-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="c1b32-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c1b32-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c1b32-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c1b32-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c1b32-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c1b32-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="c1b32-124">E_NOINTERFACE</span></span>|<span data-ttu-id="c1b32-125">El host no proporciona una implementación de `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="c1b32-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1b32-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1b32-126">Remarks</span></span>  
 <span data-ttu-id="c1b32-127">`IHostAssemblyStore`Proporciona métodos que permiten a un host enlazar a ensamblados y módulos con independencia de CLR.</span><span class="sxs-lookup"><span data-stu-id="c1b32-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="c1b32-128">Normalmente, los hosts proporcionan almacenes de ensamblados para permitir a los ensamblados que se va a cargar desde formatos que no sea el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="c1b32-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1b32-129">Si el host no implementa `IHostAssemblyStore`, `GetAssemblyStore` debe devolver un valor HRESULT de E_NOINTERFACE y debe establecer `ppAssemblyStore` en null.</span><span class="sxs-lookup"><span data-stu-id="c1b32-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1b32-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1b32-130">Requirements</span></span>  
 <span data-ttu-id="c1b32-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1b32-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1b32-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1b32-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1b32-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1b32-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1b32-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1b32-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1b32-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1b32-135">See Also</span></span>  
 [<span data-ttu-id="c1b32-136">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1b32-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="c1b32-137">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1b32-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
