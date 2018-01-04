---
title: "Método ICorDebugDataTarget2::CreateVirtualUnwinder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bffbf95fc38cba6f311e0641b35e2696bd34099
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="f582e-102">Método ICorDebugDataTarget2::CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="f582e-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="f582e-103">Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).</span><span class="sxs-lookup"><span data-stu-id="f582e-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f582e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f582e-104">Syntax</span></span>  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f582e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f582e-105">Parameters</span></span>  
 <span data-ttu-id="f582e-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="f582e-106">nativeThreadID</span></span>  
 <span data-ttu-id="f582e-107">[in] Identificador de subproceso nativo del subproceso cuya pila se va a desenredar.</span><span class="sxs-lookup"><span data-stu-id="f582e-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="f582e-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="f582e-108">contextFlags</span></span>  
 <span data-ttu-id="f582e-109">[in] Marcas que indican qué partes del contexto se definen en `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="f582e-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="f582e-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="f582e-110">cbContext</span></span>  
 <span data-ttu-id="f582e-111">[in] Tamaño de `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="f582e-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="f582e-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="f582e-112">initialContext</span></span>  
 <span data-ttu-id="f582e-113">[in] Los datos en el contexto.</span><span class="sxs-lookup"><span data-stu-id="f582e-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="f582e-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="f582e-114">ppUnwinder</span></span>  
 <span data-ttu-id="f582e-115">[out] Puntero a la dirección de un objeto de la interfaz ICorDebugVirtualUnwinder.</span><span class="sxs-lookup"><span data-stu-id="f582e-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f582e-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f582e-116">Return Value</span></span>  
 <span data-ttu-id="f582e-117">`S_OK` si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f582e-117">`S_OK` if successful.</span></span> <span data-ttu-id="f582e-118">Cualquier otro `HRESULT` indica un error.</span><span class="sxs-lookup"><span data-stu-id="f582e-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="f582e-119">Cualquier error `HRESULT` recibido por mscordbi es irrecuperable y hace que [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) métodos para devolver `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="f582e-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f582e-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f582e-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f582e-121">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f582e-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f582e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f582e-122">Requirements</span></span>  
 <span data-ttu-id="f582e-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f582e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f582e-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f582e-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f582e-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f582e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f582e-126">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f582e-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f582e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f582e-127">See Also</span></span>  
 [<span data-ttu-id="f582e-128">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f582e-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="f582e-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f582e-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
