---
description: 'Más información acerca de: ICorDebugTypeEnum:: Next (método)'
title: ICorDebugTypeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
ms.openlocfilehash: 9260f5f2d1a2d6943a705f7e7ef1ead3d2924cdc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690592"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="f4675-103">ICorDebugTypeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="f4675-103">ICorDebugTypeEnum::Next Method</span></span>

<span data-ttu-id="f4675-104">Obtiene el número de instancias de "ICorDebugType" especificadas por `celt` desde la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f4675-104">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4675-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4675-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4675-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4675-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f4675-107">de El número de `ICorDebugType` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="f4675-107">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="f4675-108">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugType` objeto.</span><span class="sxs-lookup"><span data-stu-id="f4675-108">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f4675-109">enuncia Puntero al número de `ICorDebugType` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="f4675-109">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="f4675-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="f4675-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4675-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4675-111">Requirements</span></span>  

 <span data-ttu-id="f4675-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4675-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4675-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4675-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4675-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4675-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4675-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4675-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4675-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4675-116">See also</span></span>
