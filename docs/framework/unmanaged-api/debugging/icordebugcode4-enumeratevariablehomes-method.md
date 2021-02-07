---
description: 'Más información sobre: interfaces icordebugcode4:: EnumerateVariableHomes (método)'
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
ms.openlocfilehash: 58f5f9063cd22356efd3a77ece9fb43b6b4c1062
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710964"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="0d0a4-103">Interfaces icordebugcode4:: EnumerateVariableHomes (método)</span><span class="sxs-lookup"><span data-stu-id="0d0a4-103">ICorDebugCode4::EnumerateVariableHomes Method</span></span>

<span data-ttu-id="0d0a4-104">Obtiene un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-104">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d0a4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d0a4-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d0a4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d0a4-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="0d0a4-107">Puntero a la dirección de un objeto de interfaz [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) que es un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-107">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d0a4-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d0a4-108">Remarks</span></span>  

 <span data-ttu-id="0d0a4-109">El objeto de interfaz [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) es un enumerador estándar derivado de la interfaz "ICorDebugEnum" que le permite enumerar objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0d0a4-109">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="0d0a4-110">La colección puede incluir varios objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) para la misma ranura o índice de argumento si tienen casas diferentes en distintos puntos de la función.</span><span class="sxs-lookup"><span data-stu-id="0d0a4-110">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d0a4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d0a4-111">Requirements</span></span>  

 <span data-ttu-id="0d0a4-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d0a4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d0a4-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d0a4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d0a4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d0a4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d0a4-115">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d0a4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0a4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d0a4-116">See also</span></span>

- [<span data-ttu-id="0d0a4-117">Interfaz ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="0d0a4-117">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="0d0a4-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0d0a4-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
