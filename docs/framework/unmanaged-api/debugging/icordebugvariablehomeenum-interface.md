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
ms.openlocfilehash: a9b65449747fde42f9cd770e33741ef34d33fbb8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121031"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="21aa8-102">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="21aa8-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="21aa8-103">Proporciona un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="21aa8-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21aa8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="21aa8-104">Methods</span></span>  
  
|<span data-ttu-id="21aa8-105">Método</span><span class="sxs-lookup"><span data-stu-id="21aa8-105">Method</span></span>|<span data-ttu-id="21aa8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="21aa8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21aa8-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="21aa8-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="21aa8-108">Obtiene el número especificado de instancias de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="21aa8-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21aa8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21aa8-109">Remarks</span></span>  
 <span data-ttu-id="21aa8-110">La interfaz de `ICorDebugVariableHomeEnum` implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="21aa8-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="21aa8-111">Una instancia de `ICorDebugVariableHomeEnum` se rellena con instancias de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) llamando al método [interfaces icordebugcode4:: EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="21aa8-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="21aa8-112">Cada instancia de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) de la colección representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="21aa8-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="21aa8-113">Los objetos [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) de la colección se pueden enumerar llamando al método [ICorDebugVariableHomeEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="21aa8-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21aa8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21aa8-114">Requirements</span></span>  
 <span data-ttu-id="21aa8-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21aa8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21aa8-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21aa8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21aa8-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21aa8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21aa8-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21aa8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21aa8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="21aa8-119">See also</span></span>

- [<span data-ttu-id="21aa8-120">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="21aa8-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="21aa8-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="21aa8-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
