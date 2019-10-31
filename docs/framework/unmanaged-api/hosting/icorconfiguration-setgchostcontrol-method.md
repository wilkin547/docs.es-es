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
ms.openlocfilehash: 5a32fb0480e76f47495590a29c329f54722e2dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127775"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="e01f6-102">ICorConfiguration::SetGCHostControl (Método)</span><span class="sxs-lookup"><span data-stu-id="e01f6-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="e01f6-103">Establece la interfaz de devolución de llamada que va a utilizar el recolector de elementos no utilizados para solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="e01f6-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e01f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e01f6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e01f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e01f6-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="e01f6-106">de Un puntero a un objeto [igchostcontrol (](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) que permite al recolector de elementos no utilizados solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="e01f6-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e01f6-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e01f6-107">Requirements</span></span>  
 <span data-ttu-id="e01f6-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e01f6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e01f6-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e01f6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e01f6-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e01f6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e01f6-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e01f6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e01f6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e01f6-112">See also</span></span>

- [<span data-ttu-id="e01f6-113">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e01f6-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
