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
ms.openlocfilehash: 850cbd2367dddd9f46375817e271cb8e7183cf64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121087"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="ff4a0-102">Interfaces icordebugcode4:: EnumerateVariableHomes (método)</span><span class="sxs-lookup"><span data-stu-id="ff4a0-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="ff4a0-103">Obtiene un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff4a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff4a0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff4a0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff4a0-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="ff4a0-106">Puntero a la dirección de un objeto de interfaz [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) que es un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff4a0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff4a0-107">Remarks</span></span>  
 <span data-ttu-id="ff4a0-108">El objeto de interfaz [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) es un enumerador estándar derivado de la interfaz "ICorDebugEnum" que le permite enumerar objetos [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ff4a0-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="ff4a0-109">La colección puede incluir varios objetos [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) para la misma ranura o índice de argumento si tienen casas diferentes en distintos puntos de la función.</span><span class="sxs-lookup"><span data-stu-id="ff4a0-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff4a0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff4a0-110">Requirements</span></span>  
 <span data-ttu-id="ff4a0-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff4a0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff4a0-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff4a0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff4a0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff4a0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff4a0-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff4a0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4a0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff4a0-115">See also</span></span>

- [<span data-ttu-id="ff4a0-116">ICorDebugCode4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff4a0-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="ff4a0-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ff4a0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
