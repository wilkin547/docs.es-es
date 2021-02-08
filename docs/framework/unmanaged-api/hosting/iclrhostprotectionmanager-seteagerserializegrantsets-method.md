---
description: 'Más información sobre: ICLRHostProtectionManager:: Seteagerserializegrantsets ((método)'
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
ms.openlocfilehash: 04eb00b1422523e8057c3a0fc27dfe7e49f98f08
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789923"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="35a7d-103">ICLRHostProtectionManager::SetEagerSerializeGrantSets (Método)</span><span class="sxs-lookup"><span data-stu-id="35a7d-103">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>

<span data-ttu-id="35a7d-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="35a7d-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a7d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35a7d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="35a7d-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="35a7d-106">Return Value</span></span>  
  
|<span data-ttu-id="35a7d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35a7d-107">HRESULT</span></span>|<span data-ttu-id="35a7d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="35a7d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35a7d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="35a7d-109">S_OK</span></span>|<span data-ttu-id="35a7d-110">`SetEagerSerializeGrantSets` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="35a7d-110">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="35a7d-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="35a7d-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="35a7d-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="35a7d-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="35a7d-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35a7d-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="35a7d-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="35a7d-114">The call timed out.</span></span>|  
|<span data-ttu-id="35a7d-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="35a7d-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="35a7d-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="35a7d-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="35a7d-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="35a7d-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="35a7d-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="35a7d-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="35a7d-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35a7d-119">E_FAIL</span></span>|<span data-ttu-id="35a7d-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="35a7d-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="35a7d-121">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="35a7d-121">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="35a7d-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="35a7d-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35a7d-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35a7d-123">Requirements</span></span>  

 <span data-ttu-id="35a7d-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35a7d-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a7d-125">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="35a7d-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35a7d-126">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35a7d-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35a7d-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a7d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a7d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="35a7d-128">See also</span></span>

- [<span data-ttu-id="35a7d-129">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35a7d-129">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="35a7d-130">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35a7d-130">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
