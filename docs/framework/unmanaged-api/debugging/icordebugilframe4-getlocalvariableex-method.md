---
title: ICorDebugILFrame4::GetLocalVariableEx (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: ee263e8c49cd6da7278bd2299557336629720d2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178778"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="0dc91-102">ICorDebugILFrame4::GetLocalVariableEx (Método)</span><span class="sxs-lookup"><span data-stu-id="0dc91-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="0dc91-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="0dc91-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0dc91-104">Obtiene el valor de la variable local especificada en este marco de pila de lenguaje intermedio (IL) y, opcionalmente, accede a una variable agregada en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="0dc91-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc91-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0dc91-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,
   [in] DWORD dwIndex,
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dc91-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0dc91-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="0dc91-107">[en] Un [ILCodeKind](ilcodekind-enumeration.md) miembro de enumeración que especifica si una variable agregada en la instrumentación ReJIT del generador de perfiles se incluye en el marco.</span><span class="sxs-lookup"><span data-stu-id="0dc91-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="0dc91-108">[in] Índice de la variable local en el marco de pila de IL.</span><span class="sxs-lookup"><span data-stu-id="0dc91-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="0dc91-109">[fuera] Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="0dc91-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dc91-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0dc91-110">Remarks</span></span>  
 <span data-ttu-id="0dc91-111">Este método es similar al método [GetLocalVariable,](icordebugilframe-getlocalvariable-method.md) excepto que, opcionalmente, tiene acceso a una variable agregada en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="0dc91-111">This method is similar to the [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="0dc91-112">Llamar a este `flags` método `ILCODE_ORIGINAL_IL` con un valor de es equivalente a llamar a [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); si el método se instrumenta con variables locales adicionales, no se puede acceder a esas variables.</span><span class="sxs-lookup"><span data-stu-id="0dc91-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="0dc91-113">`ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="0dc91-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="0dc91-114">Si el IL no se ha instrumentado, el método devuelve `E_INVALIDARG`.</span><span class="sxs-lookup"><span data-stu-id="0dc91-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dc91-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0dc91-115">Requirements</span></span>  
 <span data-ttu-id="0dc91-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dc91-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dc91-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dc91-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dc91-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dc91-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dc91-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dc91-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc91-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0dc91-120">See also</span></span>

- [<span data-ttu-id="0dc91-121">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0dc91-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="0dc91-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0dc91-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0dc91-123">ReJIT: Una guía de cómo hacerlo</span><span class="sxs-lookup"><span data-stu-id="0dc91-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
