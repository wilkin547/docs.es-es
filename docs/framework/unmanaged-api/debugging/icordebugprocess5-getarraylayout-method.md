---
description: 'Más información sobre: ICorDebugProcess5:: Getarraylayout ((método)'
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
ms.openlocfilehash: c82b296da3a367f5307240225a560af67a56c866
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746404"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="30c35-103">ICorDebugProcess5::GetArrayLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="30c35-103">ICorDebugProcess5::GetArrayLayout Method</span></span>

<span data-ttu-id="30c35-104">Proporciona información sobre el diseño de los tipos de matriz.</span><span class="sxs-lookup"><span data-stu-id="30c35-104">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c35-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30c35-105">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30c35-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30c35-106">Parameters</span></span>  

 `id`  
 <span data-ttu-id="30c35-107">de [COR_TYPEID](cor-typeid-structure.md) token que especifica la matriz cuyo diseño se desea.</span><span class="sxs-lookup"><span data-stu-id="30c35-107">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="30c35-108">enuncia Puntero a una estructura de [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) que contiene información sobre el diseño de la matriz en memoria.</span><span class="sxs-lookup"><span data-stu-id="30c35-108">[out] A pointer to a [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30c35-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="30c35-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30c35-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30c35-110">Requirements</span></span>  

 <span data-ttu-id="30c35-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30c35-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30c35-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30c35-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30c35-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30c35-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30c35-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30c35-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c35-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="30c35-115">See also</span></span>

- [<span data-ttu-id="30c35-116">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30c35-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="30c35-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="30c35-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
