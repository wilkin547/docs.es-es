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
ms.openlocfilehash: dd87745a29514a2f9f05aa142baae4e05d4b4a7b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206596"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="82dbc-102">Interfaz ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="82dbc-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="82dbc-103">Implementación especializada de ICorDebugFrame utilizada para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="82dbc-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82dbc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="82dbc-104">Methods</span></span>  
  
|<span data-ttu-id="82dbc-105">Método</span><span class="sxs-lookup"><span data-stu-id="82dbc-105">Method</span></span>|<span data-ttu-id="82dbc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="82dbc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82dbc-107">Método CanSetIP</span><span class="sxs-lookup"><span data-stu-id="82dbc-107">CanSetIP Method</span></span>](icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="82dbc-108">Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="82dbc-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="82dbc-109">Método GetIP</span><span class="sxs-lookup"><span data-stu-id="82dbc-109">GetIP Method</span></span>](icordebugnativeframe-getip-method.md)|<span data-ttu-id="82dbc-110">Obtiene el desplazamiento del marco de pila en código nativo.</span><span class="sxs-lookup"><span data-stu-id="82dbc-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="82dbc-111">Método GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="82dbc-111">GetLocalDoubleRegisterValue Method</span></span>](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="82dbc-112">Obtiene un puntero a un ICorDebugValue que representa el valor de un argumento o una variable local almacenados en dos registros de memoria de un marco nativo.</span><span class="sxs-lookup"><span data-stu-id="82dbc-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="82dbc-113">Método GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="82dbc-113">GetLocalMemoryRegisterValue Method</span></span>](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="82dbc-114">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, cuyos bits bajos se almacenan en el registro especificado y los bits altos se almacenan en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="82dbc-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="82dbc-115">Método GetLocalMemoryValue</span><span class="sxs-lookup"><span data-stu-id="82dbc-115">GetLocalMemoryValue Method</span></span>](icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="82dbc-116">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local almacenada en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="82dbc-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="82dbc-117">Método GetLocalRegisterMemoryValue</span><span class="sxs-lookup"><span data-stu-id="82dbc-117">GetLocalRegisterMemoryValue Method</span></span>](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="82dbc-118">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, cuyos bits altos se almacenan en el registro especificado y los bits bajos se almacenan en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="82dbc-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="82dbc-119">Método GetLocalRegisterValue</span><span class="sxs-lookup"><span data-stu-id="82dbc-119">GetLocalRegisterValue Method</span></span>](icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="82dbc-120">Obtiene un puntero a un `ICorDebugValue` que representa el valor de un argumento o una variable local almacenada en el registro nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="82dbc-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="82dbc-121">GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="82dbc-121">GetRegisterSet Method</span></span>](icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="82dbc-122">Obtiene un puntero a un [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para este `ICorDebugNativeFrame` .</span><span class="sxs-lookup"><span data-stu-id="82dbc-122">Gets a pointer to an [ICorDebugRegisterSet](icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="82dbc-123">SetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="82dbc-123">SetIP Method</span></span>](icordebugnativeframe-setip-method.md)|<span data-ttu-id="82dbc-124">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="82dbc-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82dbc-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="82dbc-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82dbc-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="82dbc-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82dbc-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82dbc-127">Requirements</span></span>  
 <span data-ttu-id="82dbc-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82dbc-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82dbc-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82dbc-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82dbc-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82dbc-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82dbc-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82dbc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82dbc-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82dbc-132">See also</span></span>

- [<span data-ttu-id="82dbc-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="82dbc-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
