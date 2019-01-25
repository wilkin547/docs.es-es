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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 886e47028ec445b0a96af367afccd09c0759d0d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727604"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="30e5a-102">IHostSecurityManager::OpenThreadToken (Método)</span><span class="sxs-lookup"><span data-stu-id="30e5a-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="30e5a-103">Se abre el token de acceso discrecional asociado con el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="30e5a-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30e5a-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30e5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30e5a-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="30e5a-106">[in] Una máscara de valores de acceso que especifican los tipos de acceso para el token de subproceso solicitados.</span><span class="sxs-lookup"><span data-stu-id="30e5a-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="30e5a-107">Estos valores se definen en Win32 `OpenThreadToken` función.</span><span class="sxs-lookup"><span data-stu-id="30e5a-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="30e5a-108">Los tipos de acceso solicitados se reconcilian con la lista de control de acceso discrecional (DACL) para determinar qué tipos de acceso para conceder o denegar del token.</span><span class="sxs-lookup"><span data-stu-id="30e5a-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="30e5a-109">[in] `true` para especificar que se debe realizar la comprobación de acceso utilizando el contexto de seguridad del proceso para el subproceso que realiza la llamada; `false` para especificar que la comprobación de acceso debe realizarse utilizando el contexto de seguridad para el subproceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="30e5a-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="30e5a-110">Si el subproceso está suplantando a un cliente, el contexto de seguridad puede ser de un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="30e5a-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="30e5a-111">[out] Un puntero al token de acceso recién abierto.</span><span class="sxs-lookup"><span data-stu-id="30e5a-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30e5a-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="30e5a-112">Return Value</span></span>  
  
|<span data-ttu-id="30e5a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30e5a-113">HRESULT</span></span>|<span data-ttu-id="30e5a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="30e5a-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30e5a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="30e5a-115">S_OK</span></span>|<span data-ttu-id="30e5a-116">`OpenThreadToken` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="30e5a-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="30e5a-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30e5a-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30e5a-118">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="30e5a-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30e5a-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30e5a-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30e5a-120">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="30e5a-120">The call timed out.</span></span>|  
|<span data-ttu-id="30e5a-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30e5a-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30e5a-122">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="30e5a-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30e5a-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30e5a-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30e5a-124">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="30e5a-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30e5a-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30e5a-125">E_FAIL</span></span>|<span data-ttu-id="30e5a-126">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="30e5a-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30e5a-127">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="30e5a-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30e5a-128">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30e5a-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30e5a-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30e5a-129">Remarks</span></span>  
 <span data-ttu-id="30e5a-130">`IHostSecurityManager::OpenThreadToken` se comporta de manera similar a la función de Win32 correspondiente del mismo nombre, salvo que la función de Win32 permite que el llamador pase un identificador a un subproceso arbitrario, mientras `IHostSecurityManager::OpenThreadToken` sólo abre el token asociado al subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="30e5a-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="30e5a-131">El `HANDLE` tipo no es compatible con COM, es decir, su tamaño es específico para el sistema operativo y requiere cálculo de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="30e5a-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="30e5a-132">Por lo tanto, este token es para su uso solo dentro del proceso, entre CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="30e5a-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e5a-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30e5a-133">Requirements</span></span>  
 <span data-ttu-id="30e5a-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30e5a-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e5a-135">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30e5a-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30e5a-136">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30e5a-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30e5a-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30e5a-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e5a-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="30e5a-138">See also</span></span>
- [<span data-ttu-id="30e5a-139">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30e5a-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="30e5a-140">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30e5a-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
