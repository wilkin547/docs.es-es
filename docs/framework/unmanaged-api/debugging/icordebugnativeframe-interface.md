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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d59450540b680d6004c47fd646769e38c806024
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161270"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="5e18d-102">Interfaz ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="5e18d-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="5e18d-103">Una implementación especializada de ICorDebugFrame utilizado para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="5e18d-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e18d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5e18d-104">Methods</span></span>  
  
|<span data-ttu-id="5e18d-105">Método</span><span class="sxs-lookup"><span data-stu-id="5e18d-105">Method</span></span>|<span data-ttu-id="5e18d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e18d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e18d-107">Método CanSetIP</span><span class="sxs-lookup"><span data-stu-id="5e18d-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="5e18d-108">Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="5e18d-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="5e18d-109">Método GetIP</span><span class="sxs-lookup"><span data-stu-id="5e18d-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="5e18d-110">Obtiene el desplazamiento del marco de pila en código nativo.</span><span class="sxs-lookup"><span data-stu-id="5e18d-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="5e18d-111">Método GetLocalDoubleRegisterValue</span><span class="sxs-lookup"><span data-stu-id="5e18d-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="5e18d-112">Obtiene un puntero a ICorDebugValue que representa el valor de un argumento o una variable local almacenada en dos registros de memoria de un marco nativo.</span><span class="sxs-lookup"><span data-stu-id="5e18d-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="5e18d-113">Método GetLocalMemoryRegisterValue</span><span class="sxs-lookup"><span data-stu-id="5e18d-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="5e18d-114">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, de los cuales los bits inferiores se almacenan en el registro especificado y los bits superiores se almacenan en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="5e18d-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="5e18d-115">Método GetLocalMemoryValue</span><span class="sxs-lookup"><span data-stu-id="5e18d-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="5e18d-116">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local almacenada en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="5e18d-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="5e18d-117">Método GetLocalRegisterMemoryValue</span><span class="sxs-lookup"><span data-stu-id="5e18d-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="5e18d-118">Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, de los cuales los bits superiores se almacenan en el registro especificado y los bits inferiores se almacenan en la dirección de memoria especificada</span><span class="sxs-lookup"><span data-stu-id="5e18d-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="5e18d-119">Método GetLocalRegisterValue</span><span class="sxs-lookup"><span data-stu-id="5e18d-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="5e18d-120">Obtiene un puntero a un `ICorDebugValue` que representa el valor de un argumento o una variable local almacenada en el registro nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="5e18d-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="5e18d-121">Método GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="5e18d-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="5e18d-122">Obtiene un puntero a un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) que representa el conjunto de registros para este `ICorDebugNativeFrame`.</span><span class="sxs-lookup"><span data-stu-id="5e18d-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="5e18d-123">Método SetIP</span><span class="sxs-lookup"><span data-stu-id="5e18d-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="5e18d-124">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.</span><span class="sxs-lookup"><span data-stu-id="5e18d-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e18d-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e18d-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e18d-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5e18d-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e18d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e18d-127">Requirements</span></span>  
 <span data-ttu-id="5e18d-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e18d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e18d-129">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e18d-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e18d-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e18d-130">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5e18d-131">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5e18d-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5e18d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e18d-132">See also</span></span>

- [<span data-ttu-id="5e18d-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5e18d-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
