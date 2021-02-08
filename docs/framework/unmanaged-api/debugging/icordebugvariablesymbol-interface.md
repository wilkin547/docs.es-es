---
description: 'Más información acerca de: interfaz ICorDebugVariableSymbol'
title: Interfaz ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: fa3fc1f318627e9175a3066c3bd3eac00929ea60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790547"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="72ec2-103">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="72ec2-103">ICorDebugVariableSymbol Interface</span></span>

<span data-ttu-id="72ec2-104">Recupera la información de símbolos de depuración para una variable.</span><span class="sxs-lookup"><span data-stu-id="72ec2-104">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72ec2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="72ec2-105">Methods</span></span>  
  
|<span data-ttu-id="72ec2-106">Método</span><span class="sxs-lookup"><span data-stu-id="72ec2-106">Method</span></span>|<span data-ttu-id="72ec2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="72ec2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72ec2-108">Método GetName</span><span class="sxs-lookup"><span data-stu-id="72ec2-108">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="72ec2-109">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="72ec2-109">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="72ec2-110">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="72ec2-110">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="72ec2-111">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="72ec2-111">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="72ec2-112">Método GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="72ec2-112">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="72ec2-113">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="72ec2-113">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="72ec2-114">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="72ec2-114">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="72ec2-115">Obtiene el valor de una variable como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="72ec2-115">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="72ec2-116">Método SetValue</span><span class="sxs-lookup"><span data-stu-id="72ec2-116">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="72ec2-117">Asigna el valor de una matriz de bytes a una variable.</span><span class="sxs-lookup"><span data-stu-id="72ec2-117">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72ec2-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="72ec2-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72ec2-119">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="72ec2-119">This interface is available with .NET Native only.</span></span> <span data-ttu-id="72ec2-120">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="72ec2-120">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72ec2-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72ec2-121">Requirements</span></span>  

 <span data-ttu-id="72ec2-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72ec2-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72ec2-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72ec2-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72ec2-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72ec2-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72ec2-125">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72ec2-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ec2-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="72ec2-126">See also</span></span>

- [<span data-ttu-id="72ec2-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="72ec2-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="72ec2-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="72ec2-128">Debugging</span></span>](index.md)
