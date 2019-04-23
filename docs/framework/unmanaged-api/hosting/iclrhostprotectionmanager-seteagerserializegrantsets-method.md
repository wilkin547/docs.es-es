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
ms.openlocfilehash: 160e31859e3d58812861d4462e77d68fa18d6186
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079661"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="94ea9-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets (Método)</span><span class="sxs-lookup"><span data-stu-id="94ea9-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="94ea9-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="94ea9-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94ea9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94ea9-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="94ea9-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="94ea9-105">Return Value</span></span>  
  
|<span data-ttu-id="94ea9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94ea9-106">HRESULT</span></span>|<span data-ttu-id="94ea9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="94ea9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94ea9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="94ea9-108">S_OK</span></span>|<span data-ttu-id="94ea9-109">`SetEagerSerializeGrantSets` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="94ea9-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="94ea9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94ea9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94ea9-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="94ea9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94ea9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94ea9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94ea9-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="94ea9-113">The call timed out.</span></span>|  
|<span data-ttu-id="94ea9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94ea9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94ea9-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="94ea9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94ea9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94ea9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94ea9-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="94ea9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94ea9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94ea9-118">E_FAIL</span></span>|<span data-ttu-id="94ea9-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="94ea9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94ea9-120">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="94ea9-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94ea9-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="94ea9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94ea9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94ea9-122">Requirements</span></span>  
 <span data-ttu-id="94ea9-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94ea9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94ea9-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="94ea9-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94ea9-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94ea9-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94ea9-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94ea9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ea9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="94ea9-127">See also</span></span>

- [<span data-ttu-id="94ea9-128">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94ea9-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="94ea9-129">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94ea9-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
