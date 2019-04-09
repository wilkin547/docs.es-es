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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e67e4685320f56a4a6a8be2e3eb2e6c8065ce59
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080389"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="b78ac-102">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="b78ac-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="b78ac-103">Proporciona un enumerador para los argumentos en una función y las variables locales.</span><span class="sxs-lookup"><span data-stu-id="b78ac-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b78ac-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b78ac-104">Methods</span></span>  
  
|<span data-ttu-id="b78ac-105">Método</span><span class="sxs-lookup"><span data-stu-id="b78ac-105">Method</span></span>|<span data-ttu-id="b78ac-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b78ac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b78ac-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="b78ac-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="b78ac-108">Obtiene el número especificado de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancias que contienen información sobre las variables locales y los argumentos en una función.</span><span class="sxs-lookup"><span data-stu-id="b78ac-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b78ac-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b78ac-109">Remarks</span></span>  
 <span data-ttu-id="b78ac-110">El `ICorDebugVariableHomeEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="b78ac-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="b78ac-111">Un `ICorDebugVariableHomeEnum` instancia se rellena con [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancias mediante una llamada a la [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b78ac-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="b78ac-112">Cada [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancias de la colección representa una variable local o argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="b78ac-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="b78ac-113">El [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) se pueden enumerar los objetos de la colección mediante una llamada a la [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b78ac-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b78ac-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b78ac-114">Requirements</span></span>  
 <span data-ttu-id="b78ac-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b78ac-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b78ac-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b78ac-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b78ac-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b78ac-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b78ac-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b78ac-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b78ac-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b78ac-119">See also</span></span>

- [<span data-ttu-id="b78ac-120">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="b78ac-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="b78ac-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b78ac-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
