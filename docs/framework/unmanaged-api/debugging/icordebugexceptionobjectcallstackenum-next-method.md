---
description: 'Más información sobre: Icordebugexceptionobjectcallstackenum (:: Next (método)'
title: ICorDebugExceptionObjectCallStackEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
ms.openlocfilehash: df68eb6e4794d294fc39dd943065582dc52a58a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693322"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="29d40-103">ICorDebugExceptionObjectCallStackEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="29d40-103">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>

<span data-ttu-id="29d40-104">Obtiene el número especificado de instancias de [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que contienen información de la pila de llamadas de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="29d40-104">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29d40-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29d40-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29d40-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29d40-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="29d40-107">de El número de instancias de [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="29d40-107">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="29d40-108">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="29d40-108">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="29d40-109">enuncia Un puntero al número de instancias de [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="29d40-109">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29d40-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="29d40-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29d40-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29d40-111">Requirements</span></span>  

 <span data-ttu-id="29d40-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29d40-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29d40-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29d40-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29d40-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29d40-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29d40-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29d40-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d40-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="29d40-116">See also</span></span>

- [<span data-ttu-id="29d40-117">ICorDebugExceptionObjectCallStackEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="29d40-117">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="29d40-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="29d40-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
