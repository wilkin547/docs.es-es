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
ms.openlocfilehash: 40a6376d4f4ffd09743441df1965d0a0f0d969b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764844"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="e472c-102">ICorPublishProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="e472c-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="e472c-103">Obtiene el número especificado de procesos de la colección, empezando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="e472c-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e472c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e472c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e472c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e472c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e472c-106">[in] El número de procesos que va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="e472c-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="e472c-107">[out] Recupera un puntero a la matriz de [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objetos, cada uno de los cuales representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="e472c-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e472c-108">[out] Puntero al número de procesos devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="e472c-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="e472c-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="e472c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e472c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e472c-110">Requirements</span></span>  
 <span data-ttu-id="e472c-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e472c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e472c-112">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="e472c-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e472c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e472c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e472c-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e472c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e472c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e472c-115">See also</span></span>

- [<span data-ttu-id="e472c-116">ICorPublishProcessEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e472c-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
