---
title: Interfaz ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 3d808fd49eb7767f1f48ad4e07d8ba7e47c8f34b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679486"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="21803-102">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="21803-102">ICorDebugVariableSymbol Interface</span></span>

<span data-ttu-id="21803-103">Recupera la información de símbolos de depuración para una variable.</span><span class="sxs-lookup"><span data-stu-id="21803-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21803-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="21803-104">Methods</span></span>  
  
|<span data-ttu-id="21803-105">Método</span><span class="sxs-lookup"><span data-stu-id="21803-105">Method</span></span>|<span data-ttu-id="21803-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="21803-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21803-107">GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="21803-107">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="21803-108">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="21803-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="21803-109">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="21803-109">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="21803-110">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="21803-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="21803-111">Método GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="21803-111">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="21803-112">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="21803-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="21803-113">GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="21803-113">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="21803-114">Obtiene el valor de una variable como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="21803-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="21803-115">Método SetValue</span><span class="sxs-lookup"><span data-stu-id="21803-115">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="21803-116">Asigna el valor de una matriz de bytes a una variable.</span><span class="sxs-lookup"><span data-stu-id="21803-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21803-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21803-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21803-118">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="21803-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="21803-119">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="21803-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21803-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21803-120">Requirements</span></span>  

 <span data-ttu-id="21803-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21803-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21803-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21803-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21803-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21803-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21803-124">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21803-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21803-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21803-125">See also</span></span>

- [<span data-ttu-id="21803-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="21803-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="21803-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="21803-127">Debugging</span></span>](index.md)
