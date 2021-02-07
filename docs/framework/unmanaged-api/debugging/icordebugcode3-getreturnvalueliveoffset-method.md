---
description: 'Más información sobre: ICorDebugCode3:: GetReturnValueLiveOffset (método)'
title: ICorDebugCode3::GetReturnValueLiveOffset (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
ms.openlocfilehash: 6ec9a342805c047d7331c3ce2af2a4ffba596a26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711016"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="ce95b-103">ICorDebugCode3::GetReturnValueLiveOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="ce95b-103">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>

<span data-ttu-id="ce95b-104">Para un desplazamiento de IL especificado, obtiene los desplazamientos nativos donde se debe colocar un punto de interrupción de modo que el depurador pueda obtener el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="ce95b-104">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce95b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce95b-105">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,
    [out] ULONG32 *pFetched,
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce95b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce95b-106">Parameters</span></span>  

 `ILoffset`  
 <span data-ttu-id="ce95b-107">Desplazamiento IL.</span><span class="sxs-lookup"><span data-stu-id="ce95b-107">The IL offset.</span></span> <span data-ttu-id="ce95b-108">Debe ser un sitio de la llamada de función o la llamada de función generará un error.</span><span class="sxs-lookup"><span data-stu-id="ce95b-108">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="ce95b-109">Número de bytes disponible para almacenar `pOffsets`.</span><span class="sxs-lookup"><span data-stu-id="ce95b-109">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="ce95b-110">Un puntero al número de desplazamientos realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="ce95b-110">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="ce95b-111">Generalmente, su valor es 1, pero una sola instrucción IL puede asignarse a varias instrucciones de ensamblado `CALL`.</span><span class="sxs-lookup"><span data-stu-id="ce95b-111">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="ce95b-112">Matriz de desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="ce95b-112">An array of native offsets.</span></span> <span data-ttu-id="ce95b-113">Normalmente, `pOffsets` contiene un único desplazamiento, aunque una sola instrucción IL puede asociar varios mapas a varias instrucciones de ensamblado `CALL`.</span><span class="sxs-lookup"><span data-stu-id="ce95b-113">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce95b-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ce95b-114">Remarks</span></span>  

 <span data-ttu-id="ce95b-115">Este método se usa junto con el método [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) para obtener el valor devuelto de un método que devuelve un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="ce95b-115">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="ce95b-116">Pasar un desplazamiento IL a un sitio de la llamada de función a este método devuelve uno o varios desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="ce95b-116">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="ce95b-117">El depurador puede establecer puntos de interrupción en estos desplazamientos nativos en la función.</span><span class="sxs-lookup"><span data-stu-id="ce95b-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="ce95b-118">Cuando el depurador llega a uno de los puntos de interrupción, puede pasar el mismo desplazamiento IL que pasó a este método al método [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) para obtener el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ce95b-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="ce95b-119">A continuación, el depurador debe borrar todos los puntos de interrupción que estableció.</span><span class="sxs-lookup"><span data-stu-id="ce95b-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="ce95b-120">Los `ICorDebugCode3::GetReturnValueLiveOffset` métodos y [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) permiten obtener información del valor devuelto solo para los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="ce95b-120">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="ce95b-121">La recuperación de información de valor devuelto de tipos de valor (es decir, todos los tipos derivados de <xref:System.ValueType>) no se admite.</span><span class="sxs-lookup"><span data-stu-id="ce95b-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="ce95b-122">La función devuelve los valores `HRESULT` mostrados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce95b-122">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="ce95b-123">Valor de `HRESULT`</span><span class="sxs-lookup"><span data-stu-id="ce95b-123">`HRESULT` value</span></span>|<span data-ttu-id="ce95b-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce95b-124">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="ce95b-125">Correcto.</span><span class="sxs-lookup"><span data-stu-id="ce95b-125">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="ce95b-126">El sitio de desplazamiento IL dado no es una instrucción de llamada o la función devuelve `void`.</span><span class="sxs-lookup"><span data-stu-id="ce95b-126">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="ce95b-127">El desplazamiento IL dado es una llamada correcta, pero el tipo de valor devuelto no se admite para obtener un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ce95b-127">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="ce95b-128">El método `ICorDebugCode3::GetReturnValueLiveOffset` solo está disponible en los sistemas basados en x86 y AMD64.</span><span class="sxs-lookup"><span data-stu-id="ce95b-128">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce95b-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce95b-129">Requirements</span></span>  

 <span data-ttu-id="ce95b-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce95b-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce95b-131">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce95b-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce95b-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce95b-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce95b-133">**.NET Framework versiones:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce95b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce95b-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce95b-134">See also</span></span>

- [<span data-ttu-id="ce95b-135">Método GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="ce95b-135">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [<span data-ttu-id="ce95b-136">ICorDebugCode3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce95b-136">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
