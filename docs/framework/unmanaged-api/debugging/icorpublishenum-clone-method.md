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
ms.openlocfilehash: e9f7f1fc0f04e8cc8c69d533c1dbba380d04ebfb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140487"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="35483-102">ICorPublishEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="35483-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="35483-103">Crea una copia de este objeto [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="35483-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35483-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35483-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35483-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35483-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="35483-106">enuncia Puntero a la dirección de un objeto `ICorPublishEnum` que es una copia de este objeto `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="35483-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35483-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35483-107">Requirements</span></span>  
 <span data-ttu-id="35483-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35483-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35483-109">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="35483-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="35483-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35483-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35483-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35483-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35483-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="35483-112">See also</span></span>

- [<span data-ttu-id="35483-113">ICorPublishEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="35483-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
