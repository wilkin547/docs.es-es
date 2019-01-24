---
title: ICorPublishProcessEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e427c3919e8b714146fbe630a7e151dff10703de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582419"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="3540f-102">ICorPublishProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="3540f-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="3540f-103">Obtiene el número especificado de procesos de la colección, empezando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="3540f-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3540f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3540f-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3540f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3540f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3540f-106">[in] El número de procesos que va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="3540f-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="3540f-107">[out] Recupera un puntero a la matriz de [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objetos, cada uno de los cuales representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="3540f-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3540f-108">[out] Puntero al número de procesos devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="3540f-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="3540f-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="3540f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3540f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3540f-110">Requirements</span></span>  
 <span data-ttu-id="3540f-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3540f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3540f-112">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3540f-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3540f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3540f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3540f-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3540f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3540f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3540f-115">See also</span></span>
- [<span data-ttu-id="3540f-116">ICorPublishProcessEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3540f-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
