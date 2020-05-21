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
ms.openlocfilehash: e648b36a2b276d9335eefaf71b57ad76f9fe0def
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762388"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="aca6c-102">ICorConfiguration::SetGCHostControl (Método)</span><span class="sxs-lookup"><span data-stu-id="aca6c-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="aca6c-103">Establece la interfaz de devolución de llamada que va a utilizar el recolector de elementos no utilizados para solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="aca6c-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aca6c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aca6c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aca6c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aca6c-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="aca6c-106">de Un puntero a un objeto [igchostcontrol (](igchostcontrol-interface.md) que permite al recolector de elementos no utilizados solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="aca6c-106">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aca6c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aca6c-107">Requirements</span></span>  
 <span data-ttu-id="aca6c-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aca6c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aca6c-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aca6c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aca6c-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aca6c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aca6c-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca6c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca6c-112">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="aca6c-112">See also</span></span>

- [<span data-ttu-id="aca6c-113">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aca6c-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
