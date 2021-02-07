---
description: 'Más información acerca de: IHostAssemblyManager:: GetAssemblyStore ((método)'
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
ms.openlocfilehash: 5edfdc5481803ce0dd3a6f8f400b18e3f1600ea8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709118"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="fa89c-103">IHostAssemblyManager::GetAssemblyStore (Método)</span><span class="sxs-lookup"><span data-stu-id="fa89c-103">IHostAssemblyManager::GetAssemblyStore Method</span></span>

<span data-ttu-id="fa89c-104">Obtiene un puntero de interfaz a un [IHostAssemblyStore](ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="fa89c-104">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa89c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa89c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa89c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa89c-106">Parameters</span></span>  

 `ppAssemblyStore`  
 <span data-ttu-id="fa89c-107">enuncia Un puntero de función a una `IHostAssemblyStore` instancia de, o null, si el host no implementa `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="fa89c-107">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa89c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fa89c-108">Return Value</span></span>  
  
|<span data-ttu-id="fa89c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa89c-109">HRESULT</span></span>|<span data-ttu-id="fa89c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa89c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa89c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa89c-111">S_OK</span></span>|<span data-ttu-id="fa89c-112">`GetAssemblyStore` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fa89c-112">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="fa89c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa89c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa89c-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fa89c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fa89c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa89c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa89c-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="fa89c-116">The call timed out.</span></span>|  
|<span data-ttu-id="fa89c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa89c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa89c-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fa89c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa89c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa89c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa89c-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="fa89c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa89c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa89c-121">E_FAIL</span></span>|<span data-ttu-id="fa89c-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="fa89c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa89c-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="fa89c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa89c-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fa89c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fa89c-125">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="fa89c-125">E_NOINTERFACE</span></span>|<span data-ttu-id="fa89c-126">El host no proporciona una implementación de `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="fa89c-126">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa89c-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa89c-127">Remarks</span></span>  

 <span data-ttu-id="fa89c-128">`IHostAssemblyStore` proporciona métodos que permiten a un host enlazarse a ensamblados y módulos independientemente de CLR.</span><span class="sxs-lookup"><span data-stu-id="fa89c-128">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="fa89c-129">Normalmente, los hosts proporcionan almacenes de ensamblados para permitir que los ensamblados se carguen desde formatos distintos del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="fa89c-129">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa89c-130">Si el host no implementa `IHostAssemblyStore` , `GetAssemblyStore` debe devolver un valor HRESULT de E_NOINTERFACE y debe establecerse `ppAssemblyStore` en NULL.</span><span class="sxs-lookup"><span data-stu-id="fa89c-130">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa89c-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa89c-131">Requirements</span></span>  

 <span data-ttu-id="fa89c-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa89c-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa89c-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fa89c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa89c-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa89c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa89c-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa89c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa89c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa89c-136">See also</span></span>

- [<span data-ttu-id="fa89c-137">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa89c-137">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="fa89c-138">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa89c-138">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
