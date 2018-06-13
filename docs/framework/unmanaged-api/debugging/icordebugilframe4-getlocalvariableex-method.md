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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a82f092a0f10fd621ac4facdee201fa239e1c1b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414534"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="4327c-102">ICorDebugILFrame4::GetLocalVariableEx (Método)</span><span class="sxs-lookup"><span data-stu-id="4327c-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="4327c-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="4327c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4327c-104">Obtiene el valor de la variable local especificada en este marco de pila de lenguaje intermedio (IL) y, opcionalmente, accede a una variable agregada en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="4327c-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4327c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4327c-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4327c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4327c-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="4327c-107">[in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) miembro de enumeración que especifica si una variable agregada en la instrumentación ReJIT del generador de perfiles se incluye en el marco.</span><span class="sxs-lookup"><span data-stu-id="4327c-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="4327c-108">[in] Índice de la variable local en el marco de pila de IL.</span><span class="sxs-lookup"><span data-stu-id="4327c-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4327c-109">[out] Un puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="4327c-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4327c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4327c-110">Remarks</span></span>  
 <span data-ttu-id="4327c-111">Este método es similar a la [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) método, excepto que accede opcionalmente a una variable agregada en la instrumentación ReJIT del generador.</span><span class="sxs-lookup"><span data-stu-id="4327c-111">This method is similar to the [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="4327c-112">Llamar a este método con un `flags` valo `ILCODE_ORIGINAL_IL` equivale a llamar a [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); si el método está instrumentado con variables locales adicionales, no se pueden tener acceso a esas variables.</span><span class="sxs-lookup"><span data-stu-id="4327c-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="4327c-113">`ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="4327c-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="4327c-114">Si el IL no se ha instrumentado, el método devuelve `E_INVALIDARG`.</span><span class="sxs-lookup"><span data-stu-id="4327c-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4327c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4327c-115">Requirements</span></span>  
 <span data-ttu-id="4327c-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4327c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4327c-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4327c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4327c-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4327c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4327c-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4327c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4327c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4327c-120">See Also</span></span>  
 [<span data-ttu-id="4327c-121">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4327c-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="4327c-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4327c-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4327c-123">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="4327c-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
