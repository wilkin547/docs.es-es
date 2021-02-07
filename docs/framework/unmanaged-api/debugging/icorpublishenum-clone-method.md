---
description: 'Más información sobre: ICorPublishEnum:: Clone (método)'
title: ICorPublishEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: 6001f27451afdb564da6275a31256ac348bc693a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721663"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="e322b-103">ICorPublishEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="e322b-103">ICorPublishEnum::Clone Method</span></span>

<span data-ttu-id="e322b-104">Crea una copia de este objeto [ICorPublishEnum](icorpublishenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e322b-104">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e322b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e322b-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e322b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e322b-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="e322b-107">enuncia Puntero a la dirección de un `ICorPublishEnum` objeto que es una copia de este `ICorPublishEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="e322b-107">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e322b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e322b-108">Requirements</span></span>  

 <span data-ttu-id="e322b-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e322b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e322b-110">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="e322b-110">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e322b-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e322b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e322b-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e322b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e322b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e322b-113">See also</span></span>

- [<span data-ttu-id="e322b-114">ICorPublishEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e322b-114">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
