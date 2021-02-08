---
description: 'Más información acerca de: interfaz ICorDebugVariableHomeEnum'
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
ms.openlocfilehash: c56c68a6b5f9d329fe8af23f47b40fa629bfe3ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790625"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="80611-103">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="80611-103">ICorDebugVariableHomeEnum Interface</span></span>

<span data-ttu-id="80611-104">Proporciona un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="80611-104">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80611-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="80611-105">Methods</span></span>  
  
|<span data-ttu-id="80611-106">Método</span><span class="sxs-lookup"><span data-stu-id="80611-106">Method</span></span>|<span data-ttu-id="80611-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="80611-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80611-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="80611-108">Next Method</span></span>](icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="80611-109">Obtiene el número especificado de instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="80611-109">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80611-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="80611-110">Remarks</span></span>  

 <span data-ttu-id="80611-111">La `ICorDebugVariableHomeEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="80611-111">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="80611-112">Una `ICorDebugVariableHomeEnum` instancia se rellena con instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) llamando al método [interfaces icordebugcode4:: EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="80611-112">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="80611-113">Cada instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) de la colección representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="80611-113">Each [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="80611-114">Los objetos  [ICorDebugVariableHome](icordebugvariablehome-interface.md) de la colección se pueden enumerar llamando al método [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="80611-114">The  [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80611-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80611-115">Requirements</span></span>  

 <span data-ttu-id="80611-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80611-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80611-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80611-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80611-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80611-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80611-119">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80611-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80611-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="80611-120">See also</span></span>

- [<span data-ttu-id="80611-121">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="80611-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="80611-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="80611-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
