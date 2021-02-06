---
description: 'Más información sobre: ICorConfiguration:: Setgchostcontrol ((método)'
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
ms.openlocfilehash: 4d3d6e5e5275adf02f9d693234a5c8e77714fd03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636655"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="edaa4-103">ICorConfiguration::SetGCHostControl (Método)</span><span class="sxs-lookup"><span data-stu-id="edaa4-103">ICorConfiguration::SetGCHostControl Method</span></span>

<span data-ttu-id="edaa4-104">Establece la interfaz de devolución de llamada que va a utilizar el recolector de elementos no utilizados para solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="edaa4-104">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edaa4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edaa4-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edaa4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="edaa4-106">Parameters</span></span>  

 `pGCHostControl`  
 <span data-ttu-id="edaa4-107">de Un puntero a un objeto [igchostcontrol (](igchostcontrol-interface.md) que permite al recolector de elementos no utilizados solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="edaa4-107">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edaa4-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="edaa4-108">Requirements</span></span>  

 <span data-ttu-id="edaa4-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edaa4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edaa4-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="edaa4-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="edaa4-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="edaa4-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edaa4-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edaa4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edaa4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="edaa4-113">See also</span></span>

- [<span data-ttu-id="edaa4-114">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="edaa4-114">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
