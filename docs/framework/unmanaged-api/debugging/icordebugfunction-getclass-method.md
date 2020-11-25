---
title: ICorDebugFunction::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
ms.openlocfilehash: 40cb59a2ad0539764702369b13d632eddbab8174
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728165"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="06364-102">ICorDebugFunction::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="06364-102">ICorDebugFunction::GetClass Method</span></span>

<span data-ttu-id="06364-103">Obtiene un objeto ICorDebugClass que representa la clase de la que es miembro esta función.</span><span class="sxs-lookup"><span data-stu-id="06364-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06364-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06364-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06364-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06364-105">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="06364-106">enuncia Puntero a la dirección del `ICorDebugClass` objeto que representa la clase, o null si esta función no es un miembro de una clase.</span><span class="sxs-lookup"><span data-stu-id="06364-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06364-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06364-107">Requirements</span></span>  

 <span data-ttu-id="06364-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06364-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06364-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06364-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06364-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06364-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06364-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06364-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
