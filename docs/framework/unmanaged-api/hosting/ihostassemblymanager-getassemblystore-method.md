---
title: IHostAssemblyManager::GetAssemblyStore (Método)
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 194b40b0873cee848124a5afc9a47740d59969c8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779457"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="7af16-102">IHostAssemblyManager::GetAssemblyStore (Método)</span><span class="sxs-lookup"><span data-stu-id="7af16-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="7af16-103">Obtiene un puntero de interfaz a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="7af16-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7af16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7af16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7af16-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7af16-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="7af16-106">[out] Un puntero de función a un `IHostAssemblyStore` de instancia o null si el host no implementa `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="7af16-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7af16-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7af16-107">Return Value</span></span>  
  
|<span data-ttu-id="7af16-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7af16-108">HRESULT</span></span>|<span data-ttu-id="7af16-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7af16-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7af16-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7af16-110">S_OK</span></span>|<span data-ttu-id="7af16-111">`GetAssemblyStore` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7af16-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="7af16-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7af16-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7af16-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7af16-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7af16-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7af16-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7af16-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7af16-115">The call timed out.</span></span>|  
|<span data-ttu-id="7af16-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7af16-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7af16-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7af16-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7af16-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7af16-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7af16-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="7af16-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7af16-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7af16-120">E_FAIL</span></span>|<span data-ttu-id="7af16-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="7af16-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7af16-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7af16-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7af16-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7af16-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7af16-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="7af16-124">E_NOINTERFACE</span></span>|<span data-ttu-id="7af16-125">El host no proporciona una implementación de `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="7af16-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7af16-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7af16-126">Remarks</span></span>  
 <span data-ttu-id="7af16-127">`IHostAssemblyStore` Proporciona métodos que permiten a un host enlazar a ensamblados y módulos con independencia de CLR.</span><span class="sxs-lookup"><span data-stu-id="7af16-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="7af16-128">Hosts suelen proporcionan almacenes de ensamblados para permitir a los ensamblados que se cargue desde formatos que no sea el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="7af16-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7af16-129">Si el host no implementa `IHostAssemblyStore`, `GetAssemblyStore` debe devolver un valor HRESULT de E_NOINTERFACE y debe establecer `ppAssemblyStore` en null.</span><span class="sxs-lookup"><span data-stu-id="7af16-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7af16-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7af16-130">Requirements</span></span>  
 <span data-ttu-id="7af16-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7af16-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7af16-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7af16-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7af16-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7af16-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7af16-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7af16-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7af16-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="7af16-135">See also</span></span>

- [<span data-ttu-id="7af16-136">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7af16-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="7af16-137">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7af16-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
