---
title: "ICorDebugILFrame4::GetLocalVariableEx (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.GetCodeEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eca9919555d0ee7c4398ecff51f9a6ee3936a41b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="06564-102">ICorDebugILFrame4::GetLocalVariableEx (Método)</span><span class="sxs-lookup"><span data-stu-id="06564-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="06564-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="06564-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="06564-104">Obtiene el valor de la variable local especificada en este marco de pila de lenguaje intermedio (IL) y, opcionalmente, accede a una variable agregada en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="06564-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06564-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06564-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06564-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06564-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="06564-107">[in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) miembro de enumeración que especifica si una variable agregada en la instrumentación ReJIT del generador de perfiles se incluye en el marco.</span><span class="sxs-lookup"><span data-stu-id="06564-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="06564-108">[in] Índice de la variable local en el marco de pila de IL.</span><span class="sxs-lookup"><span data-stu-id="06564-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="06564-109">[out] Un puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="06564-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06564-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06564-110">Remarks</span></span>  
 <span data-ttu-id="06564-111">Este método es similar a la [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) método, excepto que accede opcionalmente a una variable agregada en la instrumentación ReJIT del generador.</span><span class="sxs-lookup"><span data-stu-id="06564-111">This method is similar to the [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="06564-112">Llamar a este método con un `flags` valo `ILCODE_ORIGINAL_IL` equivale a llamar a [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); si el método está instrumentado con variables locales adicionales, no se pueden tener acceso a esas variables.</span><span class="sxs-lookup"><span data-stu-id="06564-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="06564-113">`ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="06564-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="06564-114">Si el IL no se ha instrumentado, el método devuelve `E_INVALIDARG`.</span><span class="sxs-lookup"><span data-stu-id="06564-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06564-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06564-115">Requirements</span></span>  
 <span data-ttu-id="06564-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06564-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06564-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06564-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06564-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06564-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06564-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06564-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06564-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="06564-120">See Also</span></span>  
 [<span data-ttu-id="06564-121">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06564-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="06564-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="06564-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="06564-123">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="06564-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
