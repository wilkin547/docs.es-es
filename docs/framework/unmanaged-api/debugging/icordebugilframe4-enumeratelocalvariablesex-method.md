---
title: ICorDebugILFrame4::EnumerateLocalVariablesEx (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f9d20eda8684a9a5ae43c6240d0f8a9722c4d97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076840"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="f581f-102">ICorDebugILFrame4::EnumerateLocalVariablesEx (Método)</span><span class="sxs-lookup"><span data-stu-id="f581f-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="f581f-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f581f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f581f-104">Obtiene un enumerador para la variable local en el marco y, opcionalmente, incluye las variables agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f581f-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f581f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f581f-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f581f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f581f-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="f581f-107">[in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) miembro de enumeración que especifica si las variables agregadas en la instrumentación ReJIT del generador de perfiles se incluyen en el marco.</span><span class="sxs-lookup"><span data-stu-id="f581f-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="f581f-108">[out] Un puntero a la dirección de un objeto "ICorDebugValueEnum" que es el enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="f581f-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f581f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f581f-109">Remarks</span></span>  
 <span data-ttu-id="f581f-110">Este método es similar a la [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) método, excepto que accede opcionalmente a las variables agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f581f-110">This method is similar to the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="f581f-111">Establecer `flags` a `ILCODE_ORIGINAL_IL` equivale a llamar a [ICorDebugILFrame:: EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="f581f-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="f581f-112">Establecer `flags` en `ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f581f-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="f581f-113">Si el lenguaje intermedio (IL) no se ha instrumentado, la enumeración está vacía y el método devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="f581f-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="f581f-114">El enumerador podría no incluir todas las variables locales en el método en ejecución, porque puede que algunas de ellas no estén activas.</span><span class="sxs-lookup"><span data-stu-id="f581f-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f581f-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f581f-115">Requirements</span></span>  
 <span data-ttu-id="f581f-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f581f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f581f-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f581f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f581f-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f581f-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f581f-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f581f-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f581f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f581f-120">See also</span></span>

- [<span data-ttu-id="f581f-121">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f581f-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="f581f-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f581f-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f581f-123">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="f581f-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
