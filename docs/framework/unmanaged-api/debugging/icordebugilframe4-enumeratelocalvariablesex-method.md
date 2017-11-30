---
title: "ICorDebugILFrame4::EnumerateLocalVariablesEx (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4551bf387c43ed6cbb2c6a37bba5ec1ec768e210
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="aa563-102">ICorDebugILFrame4::EnumerateLocalVariablesEx (Método)</span><span class="sxs-lookup"><span data-stu-id="aa563-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="aa563-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="aa563-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="aa563-104">Obtiene un enumerador para la variable local en el marco y, opcionalmente, incluye las variables agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="aa563-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa563-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa563-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa563-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa563-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="aa563-107">[in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) miembro de enumeración que especifica si las variables agregadas en la instrumentación ReJIT del generador de perfiles se incluyen en el marco.</span><span class="sxs-lookup"><span data-stu-id="aa563-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="aa563-108">[out] Un puntero a la dirección de un objeto de "ICorDebugValueEnum" que es el enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="aa563-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa563-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa563-109">Remarks</span></span>  
 <span data-ttu-id="aa563-110">Este método es similar a la [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) método, excepto que, opcionalmente, accede a las variables agregadas en la instrumentación ReJIT del generador.</span><span class="sxs-lookup"><span data-stu-id="aa563-110">This method is similar to the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="aa563-111">Establecer `flags` a `ILCODE_ORIGINAL_IL` equivale a llamar a [ICorDebugILFrame:: EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="aa563-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="aa563-112">Establecer `flags` en `ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="aa563-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="aa563-113">Si el lenguaje intermedio (IL) no se ha instrumentado, la enumeración está vacía y el método devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="aa563-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="aa563-114">El enumerador podría no incluir todas las variables locales en el método en ejecución, porque puede que algunas de ellas no estén activas.</span><span class="sxs-lookup"><span data-stu-id="aa563-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa563-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa563-115">Requirements</span></span>  
 <span data-ttu-id="aa563-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa563-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa563-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa563-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa563-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa563-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa563-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa563-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa563-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa563-120">See Also</span></span>  
 [<span data-ttu-id="aa563-121">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa563-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="aa563-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="aa563-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="aa563-123">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="aa563-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
