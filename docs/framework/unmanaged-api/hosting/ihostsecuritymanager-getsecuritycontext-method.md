---
description: 'Más información acerca de: IHostSecurityManager:: GetSecurityContext (método)'
title: IHostSecurityManager::GetSecurityContext (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
ms.openlocfilehash: 0dc9e0380d2fb218b68f6beb85fa1ccba8826d85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671571"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="eb8af-103">IHostSecurityManager::GetSecurityContext (Método)</span><span class="sxs-lookup"><span data-stu-id="eb8af-103">IHostSecurityManager::GetSecurityContext Method</span></span>

<span data-ttu-id="eb8af-104">Obtiene el [IHostSecurityContext](ihostsecuritycontext-interface.md) solicitado del host.</span><span class="sxs-lookup"><span data-stu-id="eb8af-104">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb8af-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb8af-105">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb8af-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb8af-106">Parameters</span></span>  

 `eContextType`  
 <span data-ttu-id="eb8af-107">de Uno de los valores de [econtexttype (](econtexttype-enumeration.md) , que indica el tipo de contexto de seguridad que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="eb8af-107">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="eb8af-108">enuncia Dirección de un puntero de interfaz al `IHostSecurityContext` de `eContextType` .</span><span class="sxs-lookup"><span data-stu-id="eb8af-108">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb8af-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eb8af-109">Return Value</span></span>  
  
|<span data-ttu-id="eb8af-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb8af-110">HRESULT</span></span>|<span data-ttu-id="eb8af-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb8af-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb8af-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb8af-112">S_OK</span></span>|<span data-ttu-id="eb8af-113">`GetSecurityContext` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="eb8af-113">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="eb8af-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eb8af-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eb8af-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="eb8af-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eb8af-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eb8af-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eb8af-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="eb8af-117">The call timed out.</span></span>|  
|<span data-ttu-id="eb8af-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eb8af-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eb8af-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="eb8af-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eb8af-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eb8af-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eb8af-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="eb8af-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eb8af-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eb8af-122">E_FAIL</span></span>|<span data-ttu-id="eb8af-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="eb8af-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eb8af-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="eb8af-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eb8af-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="eb8af-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb8af-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eb8af-126">Remarks</span></span>  

 <span data-ttu-id="eb8af-127">Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el código de usuario y el CLR.</span><span class="sxs-lookup"><span data-stu-id="eb8af-127">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="eb8af-128">También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="eb8af-128">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="eb8af-129">`IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para CLR.</span><span class="sxs-lookup"><span data-stu-id="eb8af-129">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="eb8af-130">CLR captura esta información y la mueve entre la distribución de elementos de trabajo del grupo de subprocesos, la ejecución del finalizador y la construcción de módulos y clases.</span><span class="sxs-lookup"><span data-stu-id="eb8af-130">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb8af-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb8af-131">Requirements</span></span>  

 <span data-ttu-id="eb8af-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb8af-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb8af-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eb8af-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb8af-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb8af-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb8af-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb8af-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb8af-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb8af-136">See also</span></span>

- [<span data-ttu-id="eb8af-137">EContextType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb8af-137">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="eb8af-138">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb8af-138">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="eb8af-139">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb8af-139">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
