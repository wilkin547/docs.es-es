---
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
ms.openlocfilehash: 66aab8081a5cce8c5ba986470bc91eb0604781a5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121512"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="71b07-102">IHostSecurityManager::GetSecurityContext (Método)</span><span class="sxs-lookup"><span data-stu-id="71b07-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="71b07-103">Obtiene el [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) solicitado del host.</span><span class="sxs-lookup"><span data-stu-id="71b07-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b07-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71b07-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71b07-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71b07-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="71b07-106">de Uno de los valores de [econtexttype (](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) , que indica el tipo de contexto de seguridad que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="71b07-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="71b07-107">enuncia Dirección de un puntero de interfaz al `IHostSecurityContext` de `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="71b07-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71b07-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71b07-108">Return Value</span></span>  
  
|<span data-ttu-id="71b07-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71b07-109">HRESULT</span></span>|<span data-ttu-id="71b07-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="71b07-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71b07-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="71b07-111">S_OK</span></span>|<span data-ttu-id="71b07-112">`GetSecurityContext` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="71b07-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="71b07-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71b07-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71b07-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="71b07-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71b07-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71b07-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71b07-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="71b07-116">The call timed out.</span></span>|  
|<span data-ttu-id="71b07-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71b07-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71b07-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="71b07-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71b07-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71b07-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71b07-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="71b07-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71b07-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71b07-121">E_FAIL</span></span>|<span data-ttu-id="71b07-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="71b07-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71b07-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="71b07-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71b07-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71b07-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71b07-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71b07-125">Remarks</span></span>  
 <span data-ttu-id="71b07-126">Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el código de usuario y el CLR.</span><span class="sxs-lookup"><span data-stu-id="71b07-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="71b07-127">También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="71b07-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="71b07-128">`IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para CLR.</span><span class="sxs-lookup"><span data-stu-id="71b07-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="71b07-129">CLR captura esta información y la mueve entre la distribución de elementos de trabajo del grupo de subprocesos, la ejecución del finalizador y la construcción de módulos y clases.</span><span class="sxs-lookup"><span data-stu-id="71b07-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71b07-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71b07-130">Requirements</span></span>  
 <span data-ttu-id="71b07-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71b07-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71b07-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71b07-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71b07-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71b07-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71b07-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71b07-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b07-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="71b07-135">See also</span></span>

- [<span data-ttu-id="71b07-136">EContextType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="71b07-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="71b07-137">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71b07-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="71b07-138">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71b07-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
