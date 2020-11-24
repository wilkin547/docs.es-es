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
ms.openlocfilehash: 936ea068f3cc5567a00af5f2bdd5f3d9cd52bc81
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681189"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="f5ee7-102">IHostAssemblyManager::GetAssemblyStore (Método)</span><span class="sxs-lookup"><span data-stu-id="f5ee7-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>

<span data-ttu-id="f5ee7-103">Obtiene un puntero de interfaz a un [IHostAssemblyStore](ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-103">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ee7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5ee7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5ee7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5ee7-105">Parameters</span></span>  

 `ppAssemblyStore`  
 <span data-ttu-id="f5ee7-106">enuncia Un puntero de función a una `IHostAssemblyStore` instancia de, o null, si el host no implementa `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="f5ee7-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5ee7-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f5ee7-107">Return Value</span></span>  
  
|<span data-ttu-id="f5ee7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5ee7-108">HRESULT</span></span>|<span data-ttu-id="f5ee7-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5ee7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5ee7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5ee7-110">S_OK</span></span>|<span data-ttu-id="f5ee7-111">`GetAssemblyStore` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="f5ee7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5ee7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5ee7-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5ee7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5ee7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5ee7-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-115">The call timed out.</span></span>|  
|<span data-ttu-id="f5ee7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5ee7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5ee7-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5ee7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5ee7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5ee7-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5ee7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5ee7-120">E_FAIL</span></span>|<span data-ttu-id="f5ee7-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5ee7-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5ee7-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f5ee7-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="f5ee7-124">E_NOINTERFACE</span></span>|<span data-ttu-id="f5ee7-125">El host no proporciona una implementación de `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="f5ee7-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5ee7-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5ee7-126">Remarks</span></span>  

 <span data-ttu-id="f5ee7-127">`IHostAssemblyStore` proporciona métodos que permiten a un host enlazarse a ensamblados y módulos independientemente de CLR.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="f5ee7-128">Normalmente, los hosts proporcionan almacenes de ensamblados para permitir que los ensamblados se carguen desde formatos distintos del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5ee7-129">Si el host no implementa `IHostAssemblyStore` , `GetAssemblyStore` debe devolver un valor HRESULT de E_NOINTERFACE y debe establecerse `ppAssemblyStore` en NULL.</span><span class="sxs-lookup"><span data-stu-id="f5ee7-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5ee7-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5ee7-130">Requirements</span></span>  

 <span data-ttu-id="f5ee7-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5ee7-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5ee7-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f5ee7-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5ee7-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5ee7-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5ee7-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5ee7-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ee7-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5ee7-135">See also</span></span>

- [<span data-ttu-id="f5ee7-136">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5ee7-136">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="f5ee7-137">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5ee7-137">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
