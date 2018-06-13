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
ms.openlocfilehash: 19a10a527c37d93d00bec799fdaa12bb0ad3fdbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423876"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="7b72c-102">ICorPublishProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="7b72c-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="7b72c-103">Obtiene el número especificado de procesos de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="7b72c-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b72c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b72c-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b72c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b72c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7b72c-106">[in] El número de procesos que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="7b72c-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="7b72c-107">[out] Recupera un puntero a la matriz de [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objetos, cada uno de los cuales representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="7b72c-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7b72c-108">[out] Puntero al número de procesos realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="7b72c-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="7b72c-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="7b72c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b72c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b72c-110">Requirements</span></span>  
 <span data-ttu-id="7b72c-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b72c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b72c-112">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="7b72c-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7b72c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b72c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b72c-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b72c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b72c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b72c-115">See Also</span></span>  
 [<span data-ttu-id="7b72c-116">ICorPublishProcessEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b72c-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
