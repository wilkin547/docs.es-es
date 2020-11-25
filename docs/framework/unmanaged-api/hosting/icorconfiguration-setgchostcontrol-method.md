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
ms.openlocfilehash: 4824fcfc53bae6c81760a23f76e83fb8ae7efd79
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715828"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="04e37-102">ICorConfiguration::SetGCHostControl (Método)</span><span class="sxs-lookup"><span data-stu-id="04e37-102">ICorConfiguration::SetGCHostControl Method</span></span>

<span data-ttu-id="04e37-103">Establece la interfaz de devolución de llamada que va a utilizar el recolector de elementos no utilizados para solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="04e37-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04e37-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04e37-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04e37-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04e37-105">Parameters</span></span>  

 `pGCHostControl`  
 <span data-ttu-id="04e37-106">de Un puntero a un objeto [igchostcontrol (](igchostcontrol-interface.md) que permite al recolector de elementos no utilizados solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="04e37-106">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04e37-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04e37-107">Requirements</span></span>  

 <span data-ttu-id="04e37-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04e37-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04e37-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04e37-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04e37-110">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04e37-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04e37-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04e37-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e37-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04e37-112">See also</span></span>

- [<span data-ttu-id="04e37-113">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04e37-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
