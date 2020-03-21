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
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178794"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="0a4bd-102">ICorDebugILFrame4::GetCodeEx (Método)</span><span class="sxs-lookup"><span data-stu-id="0a4bd-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="0a4bd-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="0a4bd-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0a4bd-104">Obtiene un puntero al código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="0a4bd-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a4bd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a4bd-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a4bd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a4bd-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="0a4bd-107">[en] Un [ilCodeKind](ilcodekind-enumeration.md) miembro de enumeración que especifica si el lenguaje intermedio (IL) definido por la solicitud ReJIT del generador de perfiles se incluye en el marco.</span><span class="sxs-lookup"><span data-stu-id="0a4bd-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="0a4bd-108">[fuera] Puntero a la dirección de un objeto "ICorDebugCode" que representa el código que se está ejecutando este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="0a4bd-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a4bd-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0a4bd-109">Remarks</span></span>  
 <span data-ttu-id="0a4bd-110">Este método es similar a la [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) método, excepto que opcionalmente tiene acceso al código definido por la solicitud ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="0a4bd-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="0a4bd-111">Llamar a este `flags` método `ILCODE_ORIGINAL_IL` con un valor de es equivalente a llamar a [GetCode](icordebugframe-getcode-method.md); si se instrumenta el método, su IL no será accesible.</span><span class="sxs-lookup"><span data-stu-id="0a4bd-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="0a4bd-112">`ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+.</span><span class="sxs-lookup"><span data-stu-id="0a4bd-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="0a4bd-113">Si la IL no `ppCode` está instrumentada, es `S_OK` **null**y el método devuelve .</span><span class="sxs-lookup"><span data-stu-id="0a4bd-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a4bd-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a4bd-114">Requirements</span></span>  
 <span data-ttu-id="0a4bd-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a4bd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a4bd-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a4bd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a4bd-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a4bd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a4bd-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a4bd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4bd-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a4bd-119">See also</span></span>

- [<span data-ttu-id="0a4bd-120">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a4bd-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="0a4bd-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0a4bd-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0a4bd-122">ReJIT: Una guía de cómo hacerlo</span><span class="sxs-lookup"><span data-stu-id="0a4bd-122">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
