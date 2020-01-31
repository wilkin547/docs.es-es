---
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
ms.openlocfilehash: afd16f1f31be9148422dd6d0be748036a8e5d99a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790657"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="31b77-102">ICorPublishEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="31b77-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="31b77-103">Crea una copia de este objeto [ICorPublishEnum](icorpublishenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="31b77-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31b77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31b77-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31b77-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="31b77-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="31b77-106">enuncia Puntero a la dirección de un objeto `ICorPublishEnum` que es una copia de este objeto `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="31b77-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31b77-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="31b77-107">Requirements</span></span>  
 <span data-ttu-id="31b77-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31b77-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31b77-109">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="31b77-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="31b77-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31b77-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31b77-111">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31b77-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b77-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="31b77-112">See also</span></span>

- [<span data-ttu-id="31b77-113">ICorPublishEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="31b77-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
