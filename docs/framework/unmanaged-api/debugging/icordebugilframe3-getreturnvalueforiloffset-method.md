---
description: 'Más información sobre: ICorDebugILFrame3:: GetReturnValueForILOffset (método)'
title: ICorDebugILFrame3::GetReturnValueForILOffset (Método)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
ms.openlocfilehash: 4be4cb3a108394f2701f6690b06f6c2252ae25cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791275"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="0f000-103">ICorDebugILFrame3::GetReturnValueForILOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="0f000-103">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>

<span data-ttu-id="0f000-104">Obtiene un objeto "ICorDebugValue" que encapsula el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="0f000-104">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f000-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f000-105">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f000-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f000-106">Parameters</span></span>  

 `ILOffset`  
 <span data-ttu-id="0f000-107">Desplazamiento IL.</span><span class="sxs-lookup"><span data-stu-id="0f000-107">The IL offset.</span></span> <span data-ttu-id="0f000-108">Consulte la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="0f000-108">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="0f000-109">Puntero a la dirección de un objeto de interfaz "ICorDebugValue" que proporciona información sobre el valor devuelto de una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="0f000-109">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f000-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f000-110">Remarks</span></span>  

 <span data-ttu-id="0f000-111">Este método se usa junto con el método [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) para obtener el valor devuelto de un método.</span><span class="sxs-lookup"><span data-stu-id="0f000-111">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="0f000-112">Resulta especialmente útil en el caso de los métodos cuyos valores devueltos se omiten, como en los dos ejemplos de código siguientes.</span><span class="sxs-lookup"><span data-stu-id="0f000-112">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="0f000-113">El primer ejemplo llama al método <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>, pero omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0f000-113">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="0f000-114">El segundo ejemplo muestra un problema mucho más común de depuración.</span><span class="sxs-lookup"><span data-stu-id="0f000-114">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="0f000-115">Dado que se usa un método como argumento en una llamada al método, solo se puede tener acceso al valor devuelto cuando el depurador recorre el método llamado.</span><span class="sxs-lookup"><span data-stu-id="0f000-115">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="0f000-116">En muchos casos, especialmente cuando el método al que se llama se define en una biblioteca externa, eso no es posible.</span><span class="sxs-lookup"><span data-stu-id="0f000-116">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="0f000-117">Si pasa el método [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) un desplazamiento Il a un sitio de llamada de función, devuelve uno o varios desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="0f000-117">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="0f000-118">El depurador puede establecer puntos de interrupción en estos desplazamientos nativos en la función.</span><span class="sxs-lookup"><span data-stu-id="0f000-118">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="0f000-119">Cuando el depurador llega a uno de los puntos de interrupción, podrá pasar el mismo desplazamiento IL que pasó a este método para obtener el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0f000-119">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="0f000-120">A continuación, el depurador debe borrar todos los puntos de interrupción que estableció.</span><span class="sxs-lookup"><span data-stu-id="0f000-120">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="0f000-121">El método y los métodos [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) `ICorDebugILFrame3::GetReturnValueForILOffset` permiten obtener información del valor devuelto solo para los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="0f000-121">The [ICorDebugCode3::GetReturnValueLiveOffset Method](icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="0f000-122">La recuperación de información de valor devuelto de tipos de valor (es decir, todos los tipos derivados de <xref:System.ValueType>) no se admite.</span><span class="sxs-lookup"><span data-stu-id="0f000-122">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="0f000-123">El desplazamiento IL especificado por el `ILOffset` parámetro debe estar en un sitio de llamada de función y el código depurado debe detenerse en un punto de interrupción establecido en el desplazamiento nativo devuelto por el método [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) para el mismo desplazamiento Il.</span><span class="sxs-lookup"><span data-stu-id="0f000-123">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="0f000-124">Si el código que se está depurando no se detiene en la ubicación correcta para el desplazamiento IL especificado, se producirá un error en la API.</span><span class="sxs-lookup"><span data-stu-id="0f000-124">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="0f000-125">Si la llamada de función no devuelve un valor, se producirá un error en la API.</span><span class="sxs-lookup"><span data-stu-id="0f000-125">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="0f000-126">El método `ICorDebugILFrame3::GetReturnValueForILOffset` solo está disponible en los sistemas basados en x86 y AMD64.</span><span class="sxs-lookup"><span data-stu-id="0f000-126">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f000-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f000-127">Requirements</span></span>  

 <span data-ttu-id="0f000-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f000-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f000-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f000-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f000-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f000-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f000-131">**.NET Framework versiones:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f000-131">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f000-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f000-132">See also</span></span>

- [<span data-ttu-id="0f000-133">Método GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="0f000-133">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="0f000-134">ICorDebugILFrame3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f000-134">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
