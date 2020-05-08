---
title: 'Interfaces icordebugcode4:: EnumerateVariableHomes (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 5f731b1459542c3f5378790b21f2ea576e89ad97
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893343"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="9787a-102">Interfaces icordebugcode4:: EnumerateVariableHomes (método)</span><span class="sxs-lookup"><span data-stu-id="9787a-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="9787a-103">Obtiene un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="9787a-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9787a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9787a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9787a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9787a-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="9787a-106">Puntero a la dirección de un objeto de interfaz [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) que es un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="9787a-106">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9787a-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9787a-107">Remarks</span></span>  
 <span data-ttu-id="9787a-108">El objeto de interfaz [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) es un enumerador estándar derivado de la interfaz "ICorDebugEnum" que le permite enumerar objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9787a-108">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="9787a-109">La colección puede incluir varios objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) para la misma ranura o índice de argumento si tienen casas diferentes en distintos puntos de la función.</span><span class="sxs-lookup"><span data-stu-id="9787a-109">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9787a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9787a-110">Requirements</span></span>  
 <span data-ttu-id="9787a-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9787a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9787a-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9787a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9787a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9787a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9787a-114">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9787a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9787a-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9787a-115">See also</span></span>

- [<span data-ttu-id="9787a-116">Interfaz ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="9787a-116">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="9787a-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9787a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
