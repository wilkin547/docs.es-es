---
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
ms.openlocfilehash: 7a96385ccc6e7f9089365c19bb8f150015bba81c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788526"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="c999e-102">ICorDebugILFrame3::GetReturnValueForILOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="c999e-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="c999e-103">Obtiene un objeto "ICorDebugValue" que encapsula el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="c999e-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c999e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c999e-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c999e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c999e-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="c999e-106">Desplazamiento IL.</span><span class="sxs-lookup"><span data-stu-id="c999e-106">The IL offset.</span></span> <span data-ttu-id="c999e-107">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="c999e-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="c999e-108">Puntero a la dirección de un objeto de interfaz "ICorDebugValue" que proporciona información sobre el valor devuelto de una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="c999e-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c999e-109">Notas</span><span class="sxs-lookup"><span data-stu-id="c999e-109">Remarks</span></span>  
 <span data-ttu-id="c999e-110">Este método se usa junto con el método [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) para obtener el valor devuelto de un método.</span><span class="sxs-lookup"><span data-stu-id="c999e-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="c999e-111">Resulta especialmente útil en el caso de los métodos cuyos valores devueltos se omiten, como en los dos ejemplos de código siguientes.</span><span class="sxs-lookup"><span data-stu-id="c999e-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="c999e-112">El primer ejemplo llama al método <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>, pero omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c999e-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="c999e-113">El segundo ejemplo muestra un problema mucho más común de depuración.</span><span class="sxs-lookup"><span data-stu-id="c999e-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="c999e-114">Dado que se usa un método como argumento en una llamada al método, solo se puede tener acceso al valor devuelto cuando el depurador recorre el método llamado.</span><span class="sxs-lookup"><span data-stu-id="c999e-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="c999e-115">En muchos casos, especialmente cuando el método al que se llama se define en una biblioteca externa, eso no es posible.</span><span class="sxs-lookup"><span data-stu-id="c999e-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="c999e-116">Si pasa el método [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) un desplazamiento Il a un sitio de llamada de función, devuelve uno o varios desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="c999e-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="c999e-117">El depurador puede establecer puntos de interrupción en estos desplazamientos nativos en la función.</span><span class="sxs-lookup"><span data-stu-id="c999e-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="c999e-118">Cuando el depurador llega a uno de los puntos de interrupción, podrá pasar el mismo desplazamiento IL que pasó a este método para obtener el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c999e-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="c999e-119">A continuación, el depurador debe borrar todos los puntos de interrupción que estableció.</span><span class="sxs-lookup"><span data-stu-id="c999e-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="c999e-120">El [método ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) y los métodos `ICorDebugILFrame3::GetReturnValueForILOffset` permiten obtener información del valor devuelto solo para los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="c999e-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="c999e-121">La recuperación de información de valor devuelto de tipos de valor (es decir, todos los tipos derivados de <xref:System.ValueType>) no se admite.</span><span class="sxs-lookup"><span data-stu-id="c999e-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="c999e-122">El desplazamiento IL especificado por el parámetro `ILOffset` debe estar en un sitio de llamada de función y el código depurado debe detenerse en un punto de interrupción establecido en el desplazamiento nativo devuelto por el método [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) para el mismo desplazamiento Il.</span><span class="sxs-lookup"><span data-stu-id="c999e-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="c999e-123">Si el código que se está depurando no se detiene en la ubicación correcta para el desplazamiento IL especificado, se producirá un error en la API.</span><span class="sxs-lookup"><span data-stu-id="c999e-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="c999e-124">Si la llamada de función no devuelve un valor, se producirá un error en la API.</span><span class="sxs-lookup"><span data-stu-id="c999e-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="c999e-125">El método `ICorDebugILFrame3::GetReturnValueForILOffset` solo está disponible en los sistemas basados en x86 y AMD64.</span><span class="sxs-lookup"><span data-stu-id="c999e-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c999e-126">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c999e-126">Requirements</span></span>  
 <span data-ttu-id="c999e-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c999e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c999e-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c999e-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c999e-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c999e-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c999e-130">**.NET Framework versiones:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c999e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c999e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c999e-131">See also</span></span>

- [<span data-ttu-id="c999e-132">GetReturnValueLiveOffset (método)</span><span class="sxs-lookup"><span data-stu-id="c999e-132">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="c999e-133">ICorDebugILFrame3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c999e-133">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
