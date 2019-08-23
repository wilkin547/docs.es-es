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
ms.openlocfilehash: 62965fa928522052b6885769e02c0211ca8d3fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937943"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="4e511-102">IHostAssemblyManager::GetAssemblyStore (Método)</span><span class="sxs-lookup"><span data-stu-id="4e511-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="4e511-103">Obtiene un puntero de interfaz a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="4e511-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e511-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e511-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e511-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e511-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="4e511-106">enuncia Un puntero de función a `IHostAssemblyStore` una instancia de, o null, si el host no `IHostAssemblyStore`implementa.</span><span class="sxs-lookup"><span data-stu-id="4e511-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e511-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e511-107">Return Value</span></span>  
  
|<span data-ttu-id="4e511-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e511-108">HRESULT</span></span>|<span data-ttu-id="4e511-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e511-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e511-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e511-110">S_OK</span></span>|<span data-ttu-id="4e511-111">`GetAssemblyStore`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e511-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="4e511-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4e511-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4e511-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e511-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4e511-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4e511-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4e511-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="4e511-115">The call timed out.</span></span>|  
|<span data-ttu-id="4e511-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4e511-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4e511-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4e511-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4e511-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4e511-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4e511-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="4e511-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4e511-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e511-120">E_FAIL</span></span>|<span data-ttu-id="4e511-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="4e511-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4e511-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4e511-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4e511-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4e511-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4e511-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="4e511-124">E_NOINTERFACE</span></span>|<span data-ttu-id="4e511-125">El host no proporciona una implementación de `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="4e511-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e511-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e511-126">Remarks</span></span>  
 <span data-ttu-id="4e511-127">`IHostAssemblyStore`proporciona métodos que permiten a un host enlazarse a ensamblados y módulos independientemente de CLR.</span><span class="sxs-lookup"><span data-stu-id="4e511-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="4e511-128">Normalmente, los hosts proporcionan almacenes de ensamblados para permitir que los ensamblados se carguen desde formatos distintos del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="4e511-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e511-129">Si el host no implementa `IHostAssemblyStore`, `GetAssemblyStore` debe devolver un valor HRESULT de E_NOINTERFACE y debe establecerse `ppAssemblyStore` en NULL.</span><span class="sxs-lookup"><span data-stu-id="4e511-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e511-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e511-130">Requirements</span></span>  
 <span data-ttu-id="4e511-131">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e511-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e511-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4e511-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e511-133">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e511-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e511-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e511-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e511-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e511-135">See also</span></span>

- [<span data-ttu-id="4e511-136">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e511-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="4e511-137">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e511-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
