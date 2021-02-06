---
description: 'Más información sobre: ICorDebugProcess5:: GetTypeID (método)'
title: ICorDebugProcess5::GetTypeID (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
ms.openlocfilehash: 564fc2819c9c370844111cf497d62e6d89cb28b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649720"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="b8917-103">ICorDebugProcess5::GetTypeID (Método)</span><span class="sxs-lookup"><span data-stu-id="b8917-103">ICorDebugProcess5::GetTypeID Method</span></span>

<span data-ttu-id="b8917-104">Convierte una dirección de objeto en un identificador de [COR_TYPEID](cor-typeid-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="b8917-104">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8917-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8917-105">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8917-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8917-106">Parameters</span></span>  

 `obj`  
 <span data-ttu-id="b8917-107">de Dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="b8917-107">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="b8917-108">Puntero al valor de [COR_TYPEID](cor-typeid-structure.md) que identifica el objeto.</span><span class="sxs-lookup"><span data-stu-id="b8917-108">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8917-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b8917-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8917-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8917-110">Requirements</span></span>  

 <span data-ttu-id="b8917-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8917-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8917-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8917-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8917-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8917-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8917-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8917-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8917-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8917-115">See also</span></span>

- [<span data-ttu-id="b8917-116">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8917-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="b8917-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b8917-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
