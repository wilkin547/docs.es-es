---
description: 'Más información sobre: ICorDebugILFrame4:: Enumeratelocalvariablesex ((método)'
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
ms.openlocfilehash: 8808b1ac337304ab37a35f7733b317dad274d48e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791249"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="989bc-103">ICorDebugILFrame4::EnumerateLocalVariablesEx (Método)</span><span class="sxs-lookup"><span data-stu-id="989bc-103">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>

<span data-ttu-id="989bc-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="989bc-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="989bc-105">Obtiene un enumerador para la variable local en el marco y, opcionalmente, incluye las variables agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="989bc-105">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="989bc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="989bc-106">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="989bc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="989bc-107">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="989bc-108">de Un miembro de enumeración [ILCodeKind](ilcodekind-enumeration.md) que especifica si las variables agregadas en la instrumentación ReJIT del generador de perfiles se incluyen en el marco.</span><span class="sxs-lookup"><span data-stu-id="989bc-108">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="989bc-109">enuncia Puntero a la dirección de un objeto "ICorDebugValueEnum" que es el enumerador de las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="989bc-109">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="989bc-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="989bc-110">Remarks</span></span>  

 <span data-ttu-id="989bc-111">Este método es similar al método [enumeratelocalvariables (](icordebugilframe-enumeratelocalvariables-method.md) , salvo que, de manera opcional, tiene acceso a las variables agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="989bc-111">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="989bc-112">Establecer `flags` en `ILCODE_ORIGINAL_IL` es equivalente a llamar a [ICorDebugILFrame:: enumeratelocalvariables (](icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="989bc-112">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="989bc-113">Establecer `flags` en `ILCODE_REJIT_IL` permite al depurador acceder a las variables locales agregadas en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="989bc-113">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="989bc-114">Si el lenguaje intermedio (IL) no se ha instrumentado, la enumeración está vacía y el método devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="989bc-114">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="989bc-115">El enumerador podría no incluir todas las variables locales en el método en ejecución, porque puede que algunas de ellas no estén activas.</span><span class="sxs-lookup"><span data-stu-id="989bc-115">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="989bc-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="989bc-116">Requirements</span></span>  

 <span data-ttu-id="989bc-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="989bc-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="989bc-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="989bc-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="989bc-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="989bc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="989bc-120">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="989bc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="989bc-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="989bc-121">See also</span></span>

- [<span data-ttu-id="989bc-122">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="989bc-122">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="989bc-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="989bc-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="989bc-124">ReJIT: Guía de How-To</span><span class="sxs-lookup"><span data-stu-id="989bc-124">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
