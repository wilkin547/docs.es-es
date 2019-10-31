---
title: Método ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: f9a9038bd0d268e09d8518fa50534a9959b456de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122184"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="ef853-102">Método ICorDebugDataTarget2::CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="ef853-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="ef853-103">Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).</span><span class="sxs-lookup"><span data-stu-id="ef853-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef853-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef853-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef853-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef853-105">Parameters</span></span>  
 <span data-ttu-id="ef853-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="ef853-106">nativeThreadID</span></span>  
 <span data-ttu-id="ef853-107">[in] Identificador de subproceso nativo del subproceso cuya pila se va a desenredar.</span><span class="sxs-lookup"><span data-stu-id="ef853-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="ef853-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="ef853-108">contextFlags</span></span>  
 <span data-ttu-id="ef853-109">[in] Marcas que indican qué partes del contexto se definen en `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="ef853-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="ef853-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="ef853-110">cbContext</span></span>  
 <span data-ttu-id="ef853-111">[in] Tamaño de `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="ef853-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="ef853-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="ef853-112">initialContext</span></span>  
 <span data-ttu-id="ef853-113">[in] Los datos en el contexto.</span><span class="sxs-lookup"><span data-stu-id="ef853-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="ef853-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="ef853-114">ppUnwinder</span></span>  
 <span data-ttu-id="ef853-115">[out] Puntero a la dirección de un objeto de la interfaz ICorDebugVirtualUnwinder.</span><span class="sxs-lookup"><span data-stu-id="ef853-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef853-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ef853-116">Return Value</span></span>  
 <span data-ttu-id="ef853-117">`S_OK` si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="ef853-117">`S_OK` if successful.</span></span> <span data-ttu-id="ef853-118">Cualquier otro `HRESULT` indica un error.</span><span class="sxs-lookup"><span data-stu-id="ef853-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="ef853-119">Cualquier `HRESULT` errónea recibida por mscordbi se considera fatal y hace que los métodos [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) devuelvan `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="ef853-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef853-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef853-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef853-121">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ef853-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef853-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef853-122">Requirements</span></span>  
 <span data-ttu-id="ef853-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef853-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef853-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef853-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef853-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef853-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef853-126">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef853-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef853-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef853-127">See also</span></span>

- [<span data-ttu-id="ef853-128">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef853-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="ef853-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ef853-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
