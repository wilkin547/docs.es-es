---
title: Interfaz ICorDebugNativeFrame
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: 41ac0b29ade2f78b893df72e8a17624373f6dd78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792785"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="ecdb9-102">Interfaz ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="ecdb9-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="ecdb9-103">Implementación especializada de ICorDebugFrame utilizada para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ecdb9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ecdb9-104">Methods</span></span>  
  
|<span data-ttu-id="ecdb9-105">Método</span><span class="sxs-lookup"><span data-stu-id="ecdb9-105">Method</span></span>|<span data-ttu-id="ecdb9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecdb9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ecdb9-107">CanSetIP (método)</span><span class="sxs-lookup"><span data-stu-id="ecdb9-107">CanSetIP Method</span></span>](icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="ecdb9-108">Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="ecdb9-109">GetIP (método)</span><span class="sxs-lookup"><span data-stu-id="ecdb9-109">GetIP Method</span></span>](icordebugnativeframe-getip-method.md)|<span data-ttu-id="ecdb9-110">Obtiene el desplazamiento del marco de pila en código nativo.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="ecdb9-111">GetLocalDoubleRegisterValue (método)</span><span class="sxs-lookup"><span data-stu-id="ecdb9-111">GetLocalDoubleRegisterValue Method</span></span>](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="ecdb9-112">Obtiene un puntero a un ICorDebugValue que representa el valor de un argumento o una variable local almacenados en dos registros de memoria de un marco nativo.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="ecdb9-113">GetLocalMemoryRegisterValue (método)</span><span class="sxs-lookup"><span data-stu-id="ecdb9-113">GetLocalMemoryRegisterValue Method</span></span>](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="ecdb9-114">Obtiene un puntero a una `ICorDebugValue` que representa el valor de una variable local, de la que los bits bajos se almacenan en el registro especificado y los bits altos se almacenan en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="ecdb9-115">GetLocalMemoryValue (método)</span><span class="sxs-lookup"><span data-stu-id="ecdb9-115">GetLocalMemoryValue Method</span></span>](icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="ecdb9-116">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local almacenada en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="ecdb9-117">GetLocalRegisterMemoryValue (método)</span><span class="sxs-lookup"><span data-stu-id="ecdb9-117">GetLocalRegisterMemoryValue Method</span></span>](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="ecdb9-118">Obtiene un puntero a una `ICorDebugValue` que representa el valor de una variable local, cuyos bits altos se almacenan en el registro especificado y los bits bajos se almacenan en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="ecdb9-119">GetLocalRegisterValue (método)</span><span class="sxs-lookup"><span data-stu-id="ecdb9-119">GetLocalRegisterValue Method</span></span>](icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="ecdb9-120">Obtiene un puntero a una `ICorDebugValue` que representa el valor de un argumento o una variable local almacenada en el registro nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="ecdb9-121">GetRegisterSet (método)</span><span class="sxs-lookup"><span data-stu-id="ecdb9-121">GetRegisterSet Method</span></span>](icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="ecdb9-122">Obtiene un puntero a un [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para esta `ICorDebugNativeFrame`.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-122">Gets a pointer to an [ICorDebugRegisterSet](icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="ecdb9-123">SetIP (método)</span><span class="sxs-lookup"><span data-stu-id="ecdb9-123">SetIP Method</span></span>](icordebugnativeframe-setip-method.md)|<span data-ttu-id="ecdb9-124">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecdb9-125">Notas</span><span class="sxs-lookup"><span data-stu-id="ecdb9-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ecdb9-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ecdb9-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecdb9-127">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ecdb9-127">Requirements</span></span>  
 <span data-ttu-id="ecdb9-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecdb9-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecdb9-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecdb9-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecdb9-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecdb9-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecdb9-131">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecdb9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecdb9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecdb9-132">See also</span></span>

- [<span data-ttu-id="ecdb9-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ecdb9-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
