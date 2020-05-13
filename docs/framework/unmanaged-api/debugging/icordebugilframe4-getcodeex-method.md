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
ms.openlocfilehash: 582e28c18f36b253425b1e0a2034cdd262fddd57
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213743"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="f17a8-102">ICorDebugILFrame4::GetCodeEx (Método)</span><span class="sxs-lookup"><span data-stu-id="f17a8-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="f17a8-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f17a8-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f17a8-104">Obtiene un puntero al código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f17a8-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f17a8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f17a8-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f17a8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f17a8-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="f17a8-107">de Un miembro de enumeración [ILCodeKind](ilcodekind-enumeration.md) que especifica si el lenguaje intermedio (IL) definido por la solicitud ReJIT del generador de perfiles está incluido en el marco.</span><span class="sxs-lookup"><span data-stu-id="f17a8-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="f17a8-108">enuncia Puntero a la dirección de un objeto "ICorDebugCode" que representa el código que está ejecutando este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f17a8-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f17a8-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f17a8-109">Remarks</span></span>  
 <span data-ttu-id="f17a8-110">Este método es similar al método [ICorDebugFrame:: getCode](icordebugframe-getcode-method.md) , salvo que, de manera opcional, tiene acceso al código definido por la solicitud ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f17a8-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="f17a8-111">Llamar a este método con un `flags` valor de `ILCODE_ORIGINAL_IL` es equivalente a llamar a [getCode](icordebugframe-getcode-method.md); si el método está instrumentado, no se podrá acceder a su Il.</span><span class="sxs-lookup"><span data-stu-id="f17a8-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="f17a8-112">`ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+.</span><span class="sxs-lookup"><span data-stu-id="f17a8-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="f17a8-113">Si el IL no está instrumentado, `ppCode` es **null**y el método devuelve `S_OK` .</span><span class="sxs-lookup"><span data-stu-id="f17a8-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f17a8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f17a8-114">Requirements</span></span>  
 <span data-ttu-id="f17a8-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f17a8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f17a8-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f17a8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f17a8-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f17a8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f17a8-118">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f17a8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f17a8-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f17a8-119">See also</span></span>

- [<span data-ttu-id="f17a8-120">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f17a8-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="f17a8-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f17a8-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f17a8-122">ReJIT: Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="f17a8-122">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
