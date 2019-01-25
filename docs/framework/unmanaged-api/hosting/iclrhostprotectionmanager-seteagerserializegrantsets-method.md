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
ms.openlocfilehash: 948fd78ae2839bd24a44c8c0b806e32b1da7125f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729786"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="9dfe8-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets (Método)</span><span class="sxs-lookup"><span data-stu-id="9dfe8-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="9dfe8-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="9dfe8-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dfe8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dfe8-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9dfe8-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9dfe8-105">Return Value</span></span>  
  
|<span data-ttu-id="9dfe8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9dfe8-106">HRESULT</span></span>|<span data-ttu-id="9dfe8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dfe8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9dfe8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9dfe8-108">S_OK</span></span>|<span data-ttu-id="9dfe8-109">`SetEagerSerializeGrantSets` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9dfe8-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="9dfe8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9dfe8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9dfe8-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9dfe8-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9dfe8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9dfe8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9dfe8-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="9dfe8-113">The call timed out.</span></span>|  
|<span data-ttu-id="9dfe8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9dfe8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9dfe8-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9dfe8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9dfe8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9dfe8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9dfe8-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="9dfe8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9dfe8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9dfe8-118">E_FAIL</span></span>|<span data-ttu-id="9dfe8-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="9dfe8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9dfe8-120">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9dfe8-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9dfe8-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9dfe8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9dfe8-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dfe8-122">Requirements</span></span>  
 <span data-ttu-id="9dfe8-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dfe8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dfe8-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9dfe8-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dfe8-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9dfe8-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dfe8-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dfe8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dfe8-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dfe8-127">See also</span></span>
- [<span data-ttu-id="9dfe8-128">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dfe8-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9dfe8-129">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dfe8-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
