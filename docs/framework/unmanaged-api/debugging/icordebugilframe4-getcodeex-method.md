---
title: ICorDebugILFrame4::GetCodeEx (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24be4507e8ad6cde1e9c50582e352f0fc9b12ed3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483754"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="d09e7-102">ICorDebugILFrame4::GetCodeEx (Método)</span><span class="sxs-lookup"><span data-stu-id="d09e7-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="d09e7-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="d09e7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d09e7-104">Obtiene un puntero al código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="d09e7-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d09e7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d09e7-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d09e7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d09e7-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="d09e7-107">[in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) miembro de enumeración que especifica si el lenguaje intermedio (IL) definido por solicitud de ReJIT del generador de perfiles se incluye en el marco.</span><span class="sxs-lookup"><span data-stu-id="d09e7-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="d09e7-108">[out] Un puntero a la dirección de un objeto "ICorDebugCode" que representa el código que se está ejecutando este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="d09e7-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d09e7-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d09e7-109">Remarks</span></span>  
 <span data-ttu-id="d09e7-110">Este método es similar a la [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) método, excepto que accede opcionalmente a código definido por la solicitud de ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="d09e7-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="d09e7-111">Llamar a este método con un `flags` valor `ILCODE_ORIGINAL_IL` equivale a llamar a [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); si el método está instrumentado, su IL no será accesible.</span><span class="sxs-lookup"><span data-stu-id="d09e7-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="d09e7-112">`ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+.</span><span class="sxs-lookup"><span data-stu-id="d09e7-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="d09e7-113">Si el IL no se ha instrumentado, `ppCode` es **null**, y el método devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="d09e7-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d09e7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d09e7-114">Requirements</span></span>  
 <span data-ttu-id="d09e7-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d09e7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d09e7-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d09e7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d09e7-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d09e7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d09e7-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d09e7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d09e7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d09e7-119">See Also</span></span>  
 [<span data-ttu-id="d09e7-120">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d09e7-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="d09e7-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d09e7-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d09e7-122">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="d09e7-122">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
