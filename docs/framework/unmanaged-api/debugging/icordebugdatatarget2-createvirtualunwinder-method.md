---
description: 'Más información sobre: método icordebugdatatarget2:: CreateVirtualUnwinder (método)'
title: Método ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 0646c85000f42b303769d6587354b3105e2deabd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764416"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="1a119-103">Método ICorDebugDataTarget2::CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="1a119-103">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>

<span data-ttu-id="1a119-104">Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).</span><span class="sxs-lookup"><span data-stu-id="1a119-104">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a119-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a119-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a119-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a119-106">Parameters</span></span>  

 <span data-ttu-id="1a119-107">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="1a119-107">nativeThreadID</span></span>  
 <span data-ttu-id="1a119-108">[in] Identificador de subproceso nativo del subproceso cuya pila se va a desenredar.</span><span class="sxs-lookup"><span data-stu-id="1a119-108">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="1a119-109">contextFlags</span><span class="sxs-lookup"><span data-stu-id="1a119-109">contextFlags</span></span>  
 <span data-ttu-id="1a119-110">[in] Marcas que indican qué partes del contexto se definen en `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="1a119-110">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="1a119-111">cbContext</span><span class="sxs-lookup"><span data-stu-id="1a119-111">cbContext</span></span>  
 <span data-ttu-id="1a119-112">[in] Tamaño de `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="1a119-112">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="1a119-113">initialContext</span><span class="sxs-lookup"><span data-stu-id="1a119-113">initialContext</span></span>  
 <span data-ttu-id="1a119-114">[in] Los datos en el contexto.</span><span class="sxs-lookup"><span data-stu-id="1a119-114">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="1a119-115">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="1a119-115">ppUnwinder</span></span>  
 <span data-ttu-id="1a119-116">[out] Puntero a la dirección de un objeto de la interfaz ICorDebugVirtualUnwinder.</span><span class="sxs-lookup"><span data-stu-id="1a119-116">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a119-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1a119-117">Return Value</span></span>  

 <span data-ttu-id="1a119-118">`S_OK` si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a119-118">`S_OK` if successful.</span></span> <span data-ttu-id="1a119-119">Cualquier otro `HRESULT` indica un error.</span><span class="sxs-lookup"><span data-stu-id="1a119-119">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="1a119-120">Cualquier error `HRESULT` recibido por mscordbi se considera fatal y hace que los métodos [ICorDebug](icordebug-interface.md) devuelvan `CORDBG_E_DATA_TARGET_ERROR` .</span><span class="sxs-lookup"><span data-stu-id="1a119-120">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a119-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1a119-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a119-122">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1a119-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a119-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a119-123">Requirements</span></span>  

 <span data-ttu-id="1a119-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a119-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a119-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a119-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a119-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a119-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a119-127">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a119-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a119-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a119-128">See also</span></span>

- [<span data-ttu-id="1a119-129">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="1a119-129">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="1a119-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1a119-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
