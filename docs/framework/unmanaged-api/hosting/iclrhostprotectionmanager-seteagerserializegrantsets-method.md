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
ms.openlocfilehash: e9bddaa25ba83570389a9d70ac1a9f60357f533c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432227"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="2e0e3-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets (Método)</span><span class="sxs-lookup"><span data-stu-id="2e0e3-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="2e0e3-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="2e0e3-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e0e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e0e3-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2e0e3-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2e0e3-105">Return Value</span></span>  
  
|<span data-ttu-id="2e0e3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e0e3-106">HRESULT</span></span>|<span data-ttu-id="2e0e3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e0e3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e0e3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e0e3-108">S_OK</span></span>|<span data-ttu-id="2e0e3-109">`SetEagerSerializeGrantSets` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2e0e3-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="2e0e3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e0e3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e0e3-111">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2e0e3-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e0e3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e0e3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e0e3-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2e0e3-113">The call timed out.</span></span>|  
|<span data-ttu-id="2e0e3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e0e3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e0e3-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2e0e3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e0e3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e0e3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e0e3-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="2e0e3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e0e3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e0e3-118">E_FAIL</span></span>|<span data-ttu-id="2e0e3-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="2e0e3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e0e3-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2e0e3-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e0e3-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2e0e3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e0e3-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e0e3-122">Requirements</span></span>  
 <span data-ttu-id="2e0e3-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e0e3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e0e3-124">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e0e3-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e0e3-125">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e0e3-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e0e3-126">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e0e3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0e3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e0e3-127">See Also</span></span>  
 [<span data-ttu-id="2e0e3-128">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e0e3-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="2e0e3-129">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e0e3-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
