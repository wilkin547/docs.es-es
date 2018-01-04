---
title: ICorDebugVariableSymbol (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a09fab1468435212c4437c58c113691e049b1ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="c2ef5-102">ICorDebugVariableSymbol (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2ef5-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="c2ef5-103">Recupera la información de símbolos de depuración para una variable.</span><span class="sxs-lookup"><span data-stu-id="c2ef5-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2ef5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c2ef5-104">Methods</span></span>  
  
|<span data-ttu-id="c2ef5-105">Método</span><span class="sxs-lookup"><span data-stu-id="c2ef5-105">Method</span></span>|<span data-ttu-id="c2ef5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2ef5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2ef5-107">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="c2ef5-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="c2ef5-108">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="c2ef5-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="c2ef5-109">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="c2ef5-109">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="c2ef5-110">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="c2ef5-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="c2ef5-111">GetSlotIndex (método)</span><span class="sxs-lookup"><span data-stu-id="c2ef5-111">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="c2ef5-112">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="c2ef5-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="c2ef5-113">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="c2ef5-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="c2ef5-114">Obtiene el valor de una variable como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="c2ef5-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="c2ef5-115">SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="c2ef5-115">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="c2ef5-116">Asigna el valor de una matriz de bytes a una variable.</span><span class="sxs-lookup"><span data-stu-id="c2ef5-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2ef5-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2ef5-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2ef5-118">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c2ef5-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="c2ef5-119">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="c2ef5-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2ef5-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2ef5-120">Requirements</span></span>  
 <span data-ttu-id="c2ef5-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2ef5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2ef5-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2ef5-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2ef5-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2ef5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2ef5-124">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2ef5-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ef5-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2ef5-125">See Also</span></span>  
 [<span data-ttu-id="c2ef5-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c2ef5-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c2ef5-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="c2ef5-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
