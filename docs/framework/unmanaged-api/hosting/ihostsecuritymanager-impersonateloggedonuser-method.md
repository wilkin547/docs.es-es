---
title: IHostSecurityManager::ImpersonateLoggedOnUser (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
ms.openlocfilehash: ada12a35691e0897a44f4f00e2e439fc08ef18af
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803904"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="04955-102">IHostSecurityManager::ImpersonateLoggedOnUser (Método)</span><span class="sxs-lookup"><span data-stu-id="04955-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="04955-103">Solicita que el código se ejecute con las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="04955-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04955-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04955-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04955-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04955-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="04955-106">de Un token que representa las credenciales del usuario que se va a suplantar.</span><span class="sxs-lookup"><span data-stu-id="04955-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04955-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04955-107">Return Value</span></span>  
  
|<span data-ttu-id="04955-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04955-108">HRESULT</span></span>|<span data-ttu-id="04955-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="04955-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04955-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="04955-110">S_OK</span></span>|<span data-ttu-id="04955-111">`ImpersonateLoggedOnUser`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="04955-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="04955-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04955-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04955-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="04955-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04955-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04955-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04955-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04955-115">The call timed out.</span></span>|  
|<span data-ttu-id="04955-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04955-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04955-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="04955-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04955-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04955-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04955-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="04955-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="04955-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04955-120">E_FAIL</span></span>|<span data-ttu-id="04955-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="04955-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04955-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="04955-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04955-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="04955-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04955-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="04955-124">Remarks</span></span>  
 <span data-ttu-id="04955-125">Llame a `LogonUser` o a una función de Win32 relacionada para obtener un identificador de las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="04955-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="04955-126">El `HANDLE` tipo no es compatible con com, es decir, su tamaño es específico de un sistema operativo y requiere serialización personalizada.</span><span class="sxs-lookup"><span data-stu-id="04955-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="04955-127">Por lo tanto, este token solo se usa en el proceso, entre el CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="04955-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04955-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04955-128">Requirements</span></span>  
 <span data-ttu-id="04955-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04955-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04955-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04955-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04955-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04955-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04955-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04955-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04955-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04955-133">See also</span></span>

- [<span data-ttu-id="04955-134">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04955-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="04955-135">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04955-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="04955-136">Método RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="04955-136">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)
