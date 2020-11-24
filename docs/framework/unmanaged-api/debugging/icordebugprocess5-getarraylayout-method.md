---
title: ICorDebugProcess5::GetArrayLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: 8b7fab5fc5a02f8e43dc5f6fe8fc98087859ee3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671114"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="d582d-102">ICorDebugProcess5::GetArrayLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="d582d-102">ICorDebugProcess5::GetArrayLayout Method</span></span>

<span data-ttu-id="d582d-103">Proporciona información sobre el diseño de los tipos de matriz.</span><span class="sxs-lookup"><span data-stu-id="d582d-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d582d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d582d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d582d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d582d-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="d582d-106">de [COR_TYPEID](cor-typeid-structure.md) token que especifica la matriz cuyo diseño se desea.</span><span class="sxs-lookup"><span data-stu-id="d582d-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="d582d-107">enuncia Puntero a una estructura de [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) que contiene información sobre el diseño de la matriz en memoria.</span><span class="sxs-lookup"><span data-stu-id="d582d-107">[out] A pointer to a [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d582d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d582d-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d582d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d582d-109">Requirements</span></span>  

 <span data-ttu-id="d582d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d582d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d582d-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d582d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d582d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d582d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d582d-113">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d582d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d582d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d582d-114">See also</span></span>

- [<span data-ttu-id="d582d-115">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d582d-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="d582d-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d582d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
