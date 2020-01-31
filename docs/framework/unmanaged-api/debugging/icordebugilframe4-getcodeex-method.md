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
ms.openlocfilehash: e77344a99189ec8e234129262d45698c794dc249
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788514"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="a8e8f-102">ICorDebugILFrame4::GetCodeEx (Método)</span><span class="sxs-lookup"><span data-stu-id="a8e8f-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="a8e8f-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="a8e8f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a8e8f-104">Obtiene un puntero al código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a8e8f-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e8f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8e8f-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8e8f-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="a8e8f-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="a8e8f-107">de Un miembro de enumeración [ILCodeKind](ilcodekind-enumeration.md) que especifica si el lenguaje intermedio (IL) definido por la solicitud ReJIT del generador de perfiles está incluido en el marco.</span><span class="sxs-lookup"><span data-stu-id="a8e8f-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="a8e8f-108">enuncia Puntero a la dirección de un objeto "ICorDebugCode" que representa el código que está ejecutando este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="a8e8f-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8e8f-109">Notas</span><span class="sxs-lookup"><span data-stu-id="a8e8f-109">Remarks</span></span>  
 <span data-ttu-id="a8e8f-110">Este método es similar al método [ICorDebugFrame:: getCode](icordebugframe-getcode-method.md) , salvo que, de manera opcional, tiene acceso al código definido por la solicitud ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a8e8f-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="a8e8f-111">Llamar a este método con un valor `flags` de `ILCODE_ORIGINAL_IL` es equivalente a llamar a [getCode](icordebugframe-getcode-method.md); Si el método está instrumentado, no se podrá obtener acceso a su IL.</span><span class="sxs-lookup"><span data-stu-id="a8e8f-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="a8e8f-112">`ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+.</span><span class="sxs-lookup"><span data-stu-id="a8e8f-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="a8e8f-113">Si no se instrumenta IL, `ppCode` es **null**y el método devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="a8e8f-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8e8f-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="a8e8f-114">Requirements</span></span>  
 <span data-ttu-id="a8e8f-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8e8f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8e8f-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8e8f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8e8f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8e8f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8e8f-118">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8e8f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e8f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8e8f-119">See also</span></span>

- [<span data-ttu-id="a8e8f-120">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8e8f-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="a8e8f-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a8e8f-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a8e8f-122">ReJIT: Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="a8e8f-122">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
