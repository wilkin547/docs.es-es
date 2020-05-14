---
title: Interfaz ICorDebugVariableHomeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: d5962de8cc2762f6ecf4864c5255da0fe83918e4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396528"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="ee43a-102">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="ee43a-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="ee43a-103">Proporciona un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="ee43a-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee43a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ee43a-104">Methods</span></span>  
  
|<span data-ttu-id="ee43a-105">Método</span><span class="sxs-lookup"><span data-stu-id="ee43a-105">Method</span></span>|<span data-ttu-id="ee43a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee43a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee43a-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="ee43a-107">Next Method</span></span>](icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="ee43a-108">Obtiene el número especificado de instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="ee43a-108">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee43a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee43a-109">Remarks</span></span>  
 <span data-ttu-id="ee43a-110">La `ICorDebugVariableHomeEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="ee43a-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="ee43a-111">Una `ICorDebugVariableHomeEnum` instancia se rellena con instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) llamando al método [interfaces icordebugcode4:: EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ee43a-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="ee43a-112">Cada instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) de la colección representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="ee43a-112">Each [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="ee43a-113">Los objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) de la colección se pueden enumerar llamando al método [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ee43a-113">The  [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee43a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee43a-114">Requirements</span></span>  
 <span data-ttu-id="ee43a-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee43a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee43a-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee43a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee43a-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee43a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee43a-118">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee43a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee43a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee43a-119">See also</span></span>

- [<span data-ttu-id="ee43a-120">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="ee43a-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="ee43a-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ee43a-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
