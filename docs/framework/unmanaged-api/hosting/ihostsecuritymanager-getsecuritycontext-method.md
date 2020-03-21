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
ms.openlocfilehash: 7198698edce48546c4f9a82ace18d5a6e71891ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176258"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="9ab8e-102">IHostSecurityManager::GetSecurityContext (Método)</span><span class="sxs-lookup"><span data-stu-id="9ab8e-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="9ab8e-103">Obtiene el [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) solicitado del host.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ab8e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ab8e-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ab8e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ab8e-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="9ab8e-106">[en] Uno de los [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valores, que indica qué tipo de contexto de seguridad para devolver.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="9ab8e-107">[fuera] La dirección de un `IHostSecurityContext` puntero `eContextType`de interfaz a la de .</span><span class="sxs-lookup"><span data-stu-id="9ab8e-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ab8e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ab8e-108">Return Value</span></span>  
  
|<span data-ttu-id="9ab8e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ab8e-109">HRESULT</span></span>|<span data-ttu-id="9ab8e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ab8e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ab8e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ab8e-111">S_OK</span></span>|<span data-ttu-id="9ab8e-112">`GetSecurityContext`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="9ab8e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ab8e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ab8e-114">Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ab8e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ab8e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ab8e-116">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-116">The call timed out.</span></span>|  
|<span data-ttu-id="9ab8e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ab8e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ab8e-118">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ab8e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ab8e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ab8e-120">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ab8e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ab8e-121">E_FAIL</span></span>|<span data-ttu-id="9ab8e-122">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ab8e-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ab8e-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ab8e-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9ab8e-125">Remarks</span></span>  
 <span data-ttu-id="9ab8e-126">Un host puede controlar todo el acceso de código a los tokens de subproceso mediante el código CLR y el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="9ab8e-127">También puede garantizar que la información de contexto de seguridad completa se pasa a través de operaciones asincrónicas o puntos de código con acceso de código restringido.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="9ab8e-128">`IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para CLR.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="9ab8e-129">CLR captura esta información y la mueve entre el envío de elementos de trabajo del grupo de subprocesos, la ejecución del finalizador y la construcción de módulos y clases.</span><span class="sxs-lookup"><span data-stu-id="9ab8e-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ab8e-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ab8e-130">Requirements</span></span>  
 <span data-ttu-id="9ab8e-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ab8e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ab8e-132">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ab8e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ab8e-133">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ab8e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ab8e-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ab8e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab8e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ab8e-135">See also</span></span>

- [<span data-ttu-id="9ab8e-136">EContextType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9ab8e-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="9ab8e-137">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ab8e-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="9ab8e-138">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ab8e-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
