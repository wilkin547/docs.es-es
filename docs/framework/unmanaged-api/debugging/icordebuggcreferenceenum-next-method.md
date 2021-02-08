---
description: 'Más información sobre: Icordebuggcreferenceenum (:: Next (método)'
title: ICorDebugGCReferenceEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: aec135fcb737a200d5a267529fa812c0852a24df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803703"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="39697-103">ICorDebugGCReferenceEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="39697-103">ICorDebugGCReferenceEnum::Next Method</span></span>

<span data-ttu-id="39697-104">Obtiene el número especificado de instancias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contienen información sobre los objetos que se van a recolectar como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="39697-104">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39697-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39697-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39697-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39697-106">Parameters</span></span>  

 <span data-ttu-id="39697-107">celt</span><span class="sxs-lookup"><span data-stu-id="39697-107">celt</span></span>  
 <span data-ttu-id="39697-108">de Número de raíces que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="39697-108">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="39697-109">raíces</span><span class="sxs-lookup"><span data-stu-id="39697-109">roots</span></span>  
 <span data-ttu-id="39697-110">enuncia Matriz de punteros, cada uno de los cuales apunta a un [COR_GC_REFERENCE](cor-gc-reference-structure.md) objeto que representa la raíz de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="39697-110">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="39697-111">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="39697-111">pceltFetched</span></span>  
 <span data-ttu-id="39697-112">enuncia Puntero al número de objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) realmente devueltos en `roots` .</span><span class="sxs-lookup"><span data-stu-id="39697-112">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="39697-113">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="39697-113">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39697-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39697-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39697-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39697-115">Requirements</span></span>  

 <span data-ttu-id="39697-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39697-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39697-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39697-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39697-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39697-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39697-119">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39697-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39697-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="39697-120">See also</span></span>

- [<span data-ttu-id="39697-121">ICorDebugGCReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="39697-121">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="39697-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="39697-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
