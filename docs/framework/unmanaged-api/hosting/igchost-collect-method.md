---
title: IGCHost::Collect (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
ms.openlocfilehash: ac73c462aa210927f0665cae161fd7f3e17a0cdb
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805309"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="7e63c-102">IGCHost::Collect (Método)</span><span class="sxs-lookup"><span data-stu-id="7e63c-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="7e63c-103">Obliga a que se produzca una colección para la generación dada, independientemente del estado de la recolección de elementos no utilizados actual.</span><span class="sxs-lookup"><span data-stu-id="7e63c-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e63c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e63c-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e63c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e63c-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="7e63c-106">de Generación en la que se va a realizar la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7e63c-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="7e63c-107">Un valor de-1 indica que todas las generaciones se someterán a una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7e63c-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e63c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e63c-108">Requirements</span></span>  
 <span data-ttu-id="7e63c-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e63c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e63c-110">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="7e63c-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="7e63c-111">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7e63c-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e63c-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e63c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e63c-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e63c-113">See also</span></span>

- [<span data-ttu-id="7e63c-114">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e63c-114">IGCHost Interface</span></span>](igchost-interface.md)
