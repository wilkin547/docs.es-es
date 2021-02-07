---
description: 'Más información acerca de: ICorDebugNativeFrame (interfaz)'
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
ms.openlocfilehash: e417184c9f1ca5136e1b4dba07820fd8242ae932
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729139"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="e84d0-103">Interfaz ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="e84d0-103">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="e84d0-104">Implementación especializada de ICorDebugFrame utilizada para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="e84d0-104">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e84d0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e84d0-105">Methods</span></span>  
  
|<span data-ttu-id="e84d0-106">Método</span><span class="sxs-lookup"><span data-stu-id="e84d0-106">Method</span></span>|<span data-ttu-id="e84d0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e84d0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e84d0-108">Método CanSetIP</span><span class="sxs-lookup"><span data-stu-id="e84d0-108">CanSetIP Method</span></span>](icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="e84d0-109">Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="e84d0-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="e84d0-110">Método GetIP</span><span class="sxs-lookup"><span data-stu-id="e84d0-110">GetIP Method</span></span>](icordebugnativeframe-getip-method.md)|<span data-ttu-id="e84d0-111">Obtiene el desplazamiento del marco de pila en código nativo.</span><span class="sxs-lookup"><span data-stu-id="e84d0-111">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="e84d0-112">Método GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="e84d0-112">GetLocalDoubleRegisterValue Method</span></span>](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="e84d0-113">Obtiene un puntero a un ICorDebugValue que representa el valor de un argumento o una variable local almacenados en dos registros de memoria de un marco nativo.</span><span class="sxs-lookup"><span data-stu-id="e84d0-113">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="e84d0-114">Método GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="e84d0-114">GetLocalMemoryRegisterValue Method</span></span>](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="e84d0-115">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, cuyos bits bajos se almacenan en el registro especificado y los bits altos se almacenan en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="e84d0-115">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="e84d0-116">Método GetLocalMemoryValue</span><span class="sxs-lookup"><span data-stu-id="e84d0-116">GetLocalMemoryValue Method</span></span>](icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="e84d0-117">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local almacenada en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="e84d0-117">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="e84d0-118">Método GetLocalRegisterMemoryValue</span><span class="sxs-lookup"><span data-stu-id="e84d0-118">GetLocalRegisterMemoryValue Method</span></span>](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="e84d0-119">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, cuyos bits altos se almacenan en el registro especificado y los bits bajos se almacenan en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="e84d0-119">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="e84d0-120">Método GetLocalRegisterValue</span><span class="sxs-lookup"><span data-stu-id="e84d0-120">GetLocalRegisterValue Method</span></span>](icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="e84d0-121">Obtiene un puntero a un `ICorDebugValue` que representa el valor de un argumento o una variable local almacenada en el registro nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="e84d0-121">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="e84d0-122">GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="e84d0-122">GetRegisterSet Method</span></span>](icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="e84d0-123">Obtiene un puntero a un [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para este `ICorDebugNativeFrame` .</span><span class="sxs-lookup"><span data-stu-id="e84d0-123">Gets a pointer to an [ICorDebugRegisterSet](icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="e84d0-124">SetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="e84d0-124">SetIP Method</span></span>](icordebugnativeframe-setip-method.md)|<span data-ttu-id="e84d0-125">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="e84d0-125">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e84d0-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e84d0-126">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e84d0-127">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e84d0-127">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e84d0-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e84d0-128">Requirements</span></span>  

 <span data-ttu-id="e84d0-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e84d0-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e84d0-130">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e84d0-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e84d0-131">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e84d0-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e84d0-132">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e84d0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84d0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e84d0-133">See also</span></span>

- [<span data-ttu-id="e84d0-134">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e84d0-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
