---
title: Interfaz ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 412ecbfc03378947e5a578e163034d104718bc91
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397106"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="f614d-102">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="f614d-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="f614d-103">Recupera la información de símbolos de depuración para una variable.</span><span class="sxs-lookup"><span data-stu-id="f614d-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f614d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f614d-104">Methods</span></span>  
  
|<span data-ttu-id="f614d-105">Método</span><span class="sxs-lookup"><span data-stu-id="f614d-105">Method</span></span>|<span data-ttu-id="f614d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f614d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f614d-107">Método GetName</span><span class="sxs-lookup"><span data-stu-id="f614d-107">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="f614d-108">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="f614d-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="f614d-109">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="f614d-109">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="f614d-110">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="f614d-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="f614d-111">Método GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="f614d-111">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="f614d-112">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="f614d-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="f614d-113">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="f614d-113">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="f614d-114">Obtiene el valor de una variable como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="f614d-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="f614d-115">Método SetValue</span><span class="sxs-lookup"><span data-stu-id="f614d-115">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="f614d-116">Asigna el valor de una matriz de bytes a una variable.</span><span class="sxs-lookup"><span data-stu-id="f614d-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f614d-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f614d-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f614d-118">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f614d-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f614d-119">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="f614d-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f614d-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f614d-120">Requirements</span></span>  
 <span data-ttu-id="f614d-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f614d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f614d-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f614d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f614d-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f614d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f614d-124">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f614d-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f614d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f614d-125">See also</span></span>

- [<span data-ttu-id="f614d-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f614d-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f614d-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="f614d-127">Debugging</span></span>](index.md)
