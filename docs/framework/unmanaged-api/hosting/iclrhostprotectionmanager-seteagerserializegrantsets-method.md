---
title: ICLRHostProtectionManager::SetEagerSerializeGrantSets (Método)
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f14368956ee2ffd3ae875710e1e73e2bdbee8dd7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779650"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="60086-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets (Método)</span><span class="sxs-lookup"><span data-stu-id="60086-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="60086-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="60086-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60086-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60086-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="60086-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="60086-105">Return Value</span></span>  
  
|<span data-ttu-id="60086-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60086-106">HRESULT</span></span>|<span data-ttu-id="60086-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="60086-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60086-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="60086-108">S_OK</span></span>|<span data-ttu-id="60086-109">`SetEagerSerializeGrantSets` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="60086-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="60086-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="60086-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="60086-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="60086-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="60086-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="60086-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="60086-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="60086-113">The call timed out.</span></span>|  
|<span data-ttu-id="60086-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="60086-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="60086-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="60086-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="60086-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="60086-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="60086-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="60086-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="60086-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="60086-118">E_FAIL</span></span>|<span data-ttu-id="60086-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="60086-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="60086-120">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="60086-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="60086-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="60086-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60086-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60086-122">Requirements</span></span>  
 <span data-ttu-id="60086-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60086-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60086-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="60086-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60086-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60086-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60086-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60086-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60086-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="60086-127">See also</span></span>

- [<span data-ttu-id="60086-128">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60086-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="60086-129">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60086-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
