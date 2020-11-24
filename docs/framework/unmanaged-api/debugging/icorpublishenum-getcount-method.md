---
title: ICorPublishEnum::GetCount (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
ms.openlocfilehash: a23d61da2913d8732c3860a44eb58ffadab48315
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677939"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="48d12-102">ICorPublishEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="48d12-102">ICorPublishEnum::GetCount Method</span></span>

<span data-ttu-id="48d12-103">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="48d12-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d12-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48d12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48d12-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48d12-105">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="48d12-106">enuncia Puntero al número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="48d12-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d12-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48d12-107">Requirements</span></span>  

 <span data-ttu-id="48d12-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d12-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d12-109">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="48d12-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="48d12-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48d12-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48d12-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d12-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d12-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48d12-112">See also</span></span>

- [<span data-ttu-id="48d12-113">ICorPublishEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="48d12-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
