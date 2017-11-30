---
title: "ICorDebugILFrame4::GetCodeEx (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.GetLocalVariableEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc80882353bd7a9861f4db79b83493d1cef7bfee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="0a131-102">ICorDebugILFrame4::GetCodeEx (Método)</span><span class="sxs-lookup"><span data-stu-id="0a131-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="0a131-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="0a131-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0a131-104">Obtiene un puntero al código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="0a131-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a131-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a131-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a131-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a131-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="0a131-107">[in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) miembro de enumeración que especifica si el lenguaje intermedio (IL) definido por solicitud de ReJIT del generador de perfiles se incluye en el marco.</span><span class="sxs-lookup"><span data-stu-id="0a131-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="0a131-108">[out] Un puntero a la dirección de un objeto de "ICorDebugCode" que representa el código que se está ejecutando este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="0a131-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a131-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a131-109">Remarks</span></span>  
 <span data-ttu-id="0a131-110">Este método es similar a la [ICorDebugFrame:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) método, salvo que puede acceder al código definido por la solicitud de ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="0a131-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="0a131-111">Llamar a este método con un `flags` valo `ILCODE_ORIGINAL_IL` equivale a llamar a [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); si el método está instrumentado, su IL no será accesible.</span><span class="sxs-lookup"><span data-stu-id="0a131-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="0a131-112">`ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+.</span><span class="sxs-lookup"><span data-stu-id="0a131-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="0a131-113">Si el IL no se ha instrumentado, `ppCode` es **null**, y el método devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="0a131-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a131-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a131-114">Requirements</span></span>  
 <span data-ttu-id="0a131-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a131-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a131-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a131-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a131-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a131-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a131-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a131-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a131-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a131-119">See Also</span></span>  
 [<span data-ttu-id="0a131-120">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a131-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="0a131-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0a131-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0a131-122">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="0a131-122">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
