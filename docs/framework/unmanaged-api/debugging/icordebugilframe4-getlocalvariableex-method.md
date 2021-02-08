---
description: 'Más información sobre: ICorDebugILFrame4:: Getlocalvariableex ((método)'
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
ms.openlocfilehash: 4eb6b3abbaf05c0373a487d9bd9d575b58a9af49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791223"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="a426c-103">ICorDebugILFrame4::GetLocalVariableEx (Método)</span><span class="sxs-lookup"><span data-stu-id="a426c-103">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>

<span data-ttu-id="a426c-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="a426c-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a426c-105">Obtiene el valor de la variable local especificada en este marco de pila de lenguaje intermedio (IL) y, opcionalmente, accede a una variable agregada en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a426c-105">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a426c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a426c-106">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,
   [in] DWORD dwIndex,
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a426c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a426c-107">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="a426c-108">de Miembro de la enumeración [ILCodeKind](ilcodekind-enumeration.md) que especifica si en el marco se incluye una variable agregada en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a426c-108">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="a426c-109">[in] Índice de la variable local en el marco de pila de IL.</span><span class="sxs-lookup"><span data-stu-id="a426c-109">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a426c-110">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="a426c-110">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a426c-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a426c-111">Remarks</span></span>  

 <span data-ttu-id="a426c-112">Este método es similar al método [getlocalvariable (](icordebugilframe-getlocalvariable-method.md) , salvo que, de manera opcional, tiene acceso a una variable agregada en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a426c-112">This method is similar to the [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="a426c-113">Llamar a este método con un `flags` valor de `ILCODE_ORIGINAL_IL` es equivalente a llamar a [getlocalvariable (](icordebugilframe-getlocalvariable-method.md); si el método está instrumentado con variables locales adicionales, no se puede tener acceso a esas variables.</span><span class="sxs-lookup"><span data-stu-id="a426c-113">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="a426c-114">`ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a426c-114">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="a426c-115">Si el IL no se ha instrumentado, el método devuelve `E_INVALIDARG`.</span><span class="sxs-lookup"><span data-stu-id="a426c-115">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a426c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a426c-116">Requirements</span></span>  

 <span data-ttu-id="a426c-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a426c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a426c-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a426c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a426c-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a426c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a426c-120">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a426c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a426c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a426c-121">See also</span></span>

- [<span data-ttu-id="a426c-122">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a426c-122">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="a426c-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a426c-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a426c-124">ReJIT: Guía de How-To</span><span class="sxs-lookup"><span data-stu-id="a426c-124">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
