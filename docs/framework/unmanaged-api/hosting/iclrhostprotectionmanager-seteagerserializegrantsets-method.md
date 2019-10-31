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
ms.openlocfilehash: be59acea8eadb0da9e3cd26cf17eb9e1617c3575
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141067"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="41cc6-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets (Método)</span><span class="sxs-lookup"><span data-stu-id="41cc6-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="41cc6-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="41cc6-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41cc6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41cc6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="41cc6-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="41cc6-105">Return Value</span></span>  
  
|<span data-ttu-id="41cc6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="41cc6-106">HRESULT</span></span>|<span data-ttu-id="41cc6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="41cc6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="41cc6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="41cc6-108">S_OK</span></span>|<span data-ttu-id="41cc6-109">`SetEagerSerializeGrantSets` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="41cc6-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="41cc6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="41cc6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="41cc6-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="41cc6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="41cc6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="41cc6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="41cc6-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="41cc6-113">The call timed out.</span></span>|  
|<span data-ttu-id="41cc6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="41cc6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="41cc6-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="41cc6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="41cc6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="41cc6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="41cc6-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="41cc6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="41cc6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="41cc6-118">E_FAIL</span></span>|<span data-ttu-id="41cc6-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="41cc6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="41cc6-120">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="41cc6-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="41cc6-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="41cc6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41cc6-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41cc6-122">Requirements</span></span>  
 <span data-ttu-id="41cc6-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41cc6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41cc6-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="41cc6-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="41cc6-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="41cc6-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41cc6-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41cc6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cc6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="41cc6-127">See also</span></span>

- [<span data-ttu-id="41cc6-128">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41cc6-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="41cc6-129">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41cc6-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
