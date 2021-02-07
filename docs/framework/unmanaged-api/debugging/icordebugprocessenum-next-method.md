---
description: 'Más información sobre: Icordebugprocessenum (:: Next (método)'
title: ICorDebugProcessEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: e32ff2e67f3f8a0242e0a0f93ed00229fee9cc26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691177"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="bd9d7-103">ICorDebugProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="bd9d7-103">ICorDebugProcessEnum::Next Method</span></span>

<span data-ttu-id="bd9d7-104">Obtiene el número especificado de instancias de ICorDebugProcess de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="bd9d7-104">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd9d7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd9d7-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd9d7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd9d7-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="bd9d7-107">de El número de `ICorDebugProcess` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="bd9d7-107">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="bd9d7-108">enuncia Matriz de punteros, cada uno de los cuales apunta a un `ICorDebugProcess` objeto que representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="bd9d7-108">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bd9d7-109">enuncia Puntero al número de `ICorDebugProcess` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="bd9d7-109">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="bd9d7-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="bd9d7-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd9d7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd9d7-111">Requirements</span></span>  

 <span data-ttu-id="bd9d7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd9d7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd9d7-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd9d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd9d7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd9d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd9d7-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd9d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
