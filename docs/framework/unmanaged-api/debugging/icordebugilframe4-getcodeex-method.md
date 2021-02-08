---
description: 'Más información sobre: ICorDebugILFrame4:: Getcodeex ((método)'
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
ms.openlocfilehash: 1d17dfa531354b8a4b0dd3c0d3d2eb47206900cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791236"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="f2402-103">ICorDebugILFrame4::GetCodeEx (Método)</span><span class="sxs-lookup"><span data-stu-id="f2402-103">ICorDebugILFrame4::GetCodeEx Method</span></span>

<span data-ttu-id="f2402-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f2402-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f2402-105">Obtiene un puntero al código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f2402-105">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2402-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2402-106">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2402-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2402-107">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="f2402-108">de Un miembro de enumeración [ILCodeKind](ilcodekind-enumeration.md) que especifica si el lenguaje intermedio (IL) definido por la solicitud ReJIT del generador de perfiles está incluido en el marco.</span><span class="sxs-lookup"><span data-stu-id="f2402-108">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="f2402-109">enuncia Puntero a la dirección de un objeto "ICorDebugCode" que representa el código que está ejecutando este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f2402-109">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2402-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f2402-110">Remarks</span></span>  

 <span data-ttu-id="f2402-111">Este método es similar al método [ICorDebugFrame:: getCode](icordebugframe-getcode-method.md) , salvo que, de manera opcional, tiene acceso al código definido por la solicitud ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f2402-111">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="f2402-112">Llamar a este método con un `flags` valor de `ILCODE_ORIGINAL_IL` es equivalente a llamar a [getCode](icordebugframe-getcode-method.md); si el método está instrumentado, no se podrá acceder a su Il.</span><span class="sxs-lookup"><span data-stu-id="f2402-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="f2402-113">`ILCODE_REJIT_IL` permite al depurador acceder al IL definido por la solicitud ReJIT del generador de perfiles+.</span><span class="sxs-lookup"><span data-stu-id="f2402-113">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="f2402-114">Si el IL no está instrumentado, `ppCode` es **null** y el método devuelve `S_OK` .</span><span class="sxs-lookup"><span data-stu-id="f2402-114">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2402-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2402-115">Requirements</span></span>  

 <span data-ttu-id="f2402-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2402-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2402-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2402-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2402-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2402-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2402-119">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2402-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2402-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2402-120">See also</span></span>

- [<span data-ttu-id="f2402-121">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2402-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="f2402-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f2402-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f2402-123">ReJIT: Guía de How-To</span><span class="sxs-lookup"><span data-stu-id="f2402-123">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
