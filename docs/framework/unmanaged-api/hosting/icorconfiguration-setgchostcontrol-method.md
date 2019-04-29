---
title: ICorConfiguration::SetGCHostControl (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50a92058e8a394b95c690d19f1bafdddbed8246a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763248"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="3f7d0-102">ICorConfiguration::SetGCHostControl (Método)</span><span class="sxs-lookup"><span data-stu-id="3f7d0-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="3f7d0-103">Establece la interfaz de devolución de llamada que se usará por el recolector de elementos no utilizados para solicitar al host que cambie los límites de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="3f7d0-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f7d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f7d0-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f7d0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f7d0-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="3f7d0-106">[in] Un puntero a un [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) objeto que permite que el recolector de elementos no utilizados solicitar el host para cambiar los límites de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="3f7d0-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f7d0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f7d0-107">Requirements</span></span>  
 <span data-ttu-id="3f7d0-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f7d0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f7d0-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3f7d0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f7d0-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f7d0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f7d0-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f7d0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f7d0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f7d0-112">See also</span></span>

- [<span data-ttu-id="3f7d0-113">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f7d0-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
