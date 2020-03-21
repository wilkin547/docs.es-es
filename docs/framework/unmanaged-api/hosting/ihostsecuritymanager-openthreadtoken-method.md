---
title: IHostSecurityManager::OpenThreadToken (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176271"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="112b6-102">IHostSecurityManager::OpenThreadToken (Método)</span><span class="sxs-lookup"><span data-stu-id="112b6-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="112b6-103">Abre el token de acceso discrecional asociado al subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="112b6-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="112b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="112b6-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="112b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="112b6-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="112b6-106">[en] Máscara de valores de acceso que especifican los tipos de acceso solicitados al token de subproceso.</span><span class="sxs-lookup"><span data-stu-id="112b6-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="112b6-107">Estos valores se definen `OpenThreadToken` en la función Win32.</span><span class="sxs-lookup"><span data-stu-id="112b6-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="112b6-108">Los tipos de acceso solicitados se reconcilian con la lista de control de acceso discrecional (DACL) del token para determinar qué tipos de acceso conceder o denegar.</span><span class="sxs-lookup"><span data-stu-id="112b6-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="112b6-109">[en] `true` para especificar que la comprobación de acceso debe realizarse mediante el contexto de seguridad del proceso para el subproceso que realiza la llamada; `false` para especificar que la comprobación de acceso se debe realizar mediante el contexto de seguridad para el propio subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="112b6-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="112b6-110">Si el subproceso está suplantando a un cliente, el contexto de seguridad puede ser el de un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="112b6-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="112b6-111">[fuera] Un puntero al token de acceso recién abierto.</span><span class="sxs-lookup"><span data-stu-id="112b6-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="112b6-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="112b6-112">Return Value</span></span>  
  
|<span data-ttu-id="112b6-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="112b6-113">HRESULT</span></span>|<span data-ttu-id="112b6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="112b6-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="112b6-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="112b6-115">S_OK</span></span>|<span data-ttu-id="112b6-116">`OpenThreadToken`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="112b6-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="112b6-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="112b6-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="112b6-118">Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="112b6-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="112b6-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="112b6-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="112b6-120">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="112b6-120">The call timed out.</span></span>|  
|<span data-ttu-id="112b6-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="112b6-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="112b6-122">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="112b6-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="112b6-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="112b6-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="112b6-124">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="112b6-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="112b6-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="112b6-125">E_FAIL</span></span>|<span data-ttu-id="112b6-126">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="112b6-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="112b6-127">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="112b6-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="112b6-128">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="112b6-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="112b6-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="112b6-129">Remarks</span></span>  
 <span data-ttu-id="112b6-130">`IHostSecurityManager::OpenThreadToken`se comporta de forma similar a la función Win32 correspondiente del mismo nombre, excepto que la función `IHostSecurityManager::OpenThreadToken` Win32 permite al autor de la llamada pasar un identificador a un subproceso arbitrario, mientras que abre solo el token asociado al subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="112b6-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="112b6-131">El `HANDLE` tipo no es compatible con COM, es decir, su tamaño es específico del sistema operativo y requiere el cálculo de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="112b6-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="112b6-132">Por lo tanto, este token se usa solo dentro del proceso, entre CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="112b6-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="112b6-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="112b6-133">Requirements</span></span>  
 <span data-ttu-id="112b6-134">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="112b6-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="112b6-135">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="112b6-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="112b6-136">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="112b6-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="112b6-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="112b6-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="112b6-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="112b6-138">See also</span></span>

- [<span data-ttu-id="112b6-139">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="112b6-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="112b6-140">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="112b6-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
