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
ms.openlocfilehash: ca452b230e2508f2d69c9aa38f274db506f3a906
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784087"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="661c8-102">Interfaces icordebugcode4:: EnumerateVariableHomes (método)</span><span class="sxs-lookup"><span data-stu-id="661c8-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="661c8-103">Obtiene un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="661c8-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="661c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="661c8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="661c8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="661c8-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="661c8-106">Puntero a la dirección de un objeto de interfaz [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) que es un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="661c8-106">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="661c8-107">Notas</span><span class="sxs-lookup"><span data-stu-id="661c8-107">Remarks</span></span>  
 <span data-ttu-id="661c8-108">El objeto de interfaz [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) es un enumerador estándar derivado de la interfaz "ICorDebugEnum" que le permite enumerar objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="661c8-108">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="661c8-109">La colección puede incluir varios objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) para la misma ranura o índice de argumento si tienen casas diferentes en distintos puntos de la función.</span><span class="sxs-lookup"><span data-stu-id="661c8-109">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="661c8-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="661c8-110">Requirements</span></span>  
 <span data-ttu-id="661c8-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="661c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="661c8-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="661c8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="661c8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="661c8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="661c8-114">**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="661c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661c8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="661c8-115">See also</span></span>

- [<span data-ttu-id="661c8-116">ICorDebugCode4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="661c8-116">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="661c8-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="661c8-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
