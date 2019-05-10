---
title: _EFN_StackTrace (Función)
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0074584ee5baba358db5bf3b0f2cfdd9a3d8f1d9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593538"
---
# <a name="efnstacktrace-function"></a><span data-ttu-id="019a9-102">_EFN_StackTrace (Función)</span><span class="sxs-lookup"><span data-stu-id="019a9-102">_EFN_StackTrace Function</span></span>
<span data-ttu-id="019a9-103">Proporciona una representación de texto de un seguimiento de pila administrado y una matriz de registros `CONTEXT`, uno por cada transición entre código no administrado y código administrado.</span><span class="sxs-lookup"><span data-stu-id="019a9-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="019a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="019a9-104">Syntax</span></span>  
  
```  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="019a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="019a9-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="019a9-106">[in] El cliente que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="019a9-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="019a9-107">[out] La representación de texto del seguimiento de pila.</span><span class="sxs-lookup"><span data-stu-id="019a9-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="019a9-108">[out] Un puntero al número de caracteres en `wszTextOut`.</span><span class="sxs-lookup"><span data-stu-id="019a9-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="019a9-109">[out] La matriz de contextos de transición.</span><span class="sxs-lookup"><span data-stu-id="019a9-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="019a9-110">[out] Un puntero al número de contextos de transición en la matriz.</span><span class="sxs-lookup"><span data-stu-id="019a9-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="019a9-111">[in] El tamaño de la estructura de contexto.</span><span class="sxs-lookup"><span data-stu-id="019a9-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="019a9-112">[in] Se establece en 0 o SOS_STACKTRACE_SHOWADDRESSES (0 x 01) para mostrar el registro EBP y el puntero de pila (ESP) delante de cada `module!functionname` línea.</span><span class="sxs-lookup"><span data-stu-id="019a9-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="019a9-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="019a9-113">Remarks</span></span>  
 <span data-ttu-id="019a9-114">El `_EFN_StackTrace` estructura puede llamarse desde una interfaz de programación WinDbg.</span><span class="sxs-lookup"><span data-stu-id="019a9-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="019a9-115">Los parámetros se usan como sigue:</span><span class="sxs-lookup"><span data-stu-id="019a9-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="019a9-116">Si `wszTextOut` es null y `puiTextLength` es no nulo, la función devuelve la longitud de cadena en `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="019a9-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="019a9-117">Si `wszTextOut` es no nulo, la función almacena el texto en `wszTextOut` hasta la ubicación indicada por `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="019a9-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="019a9-118">Devuelve correctamente si había espacio suficiente en el búfer, o se devuelve E_OUTOFMEMORY si el búfer no es suficientemente larga.</span><span class="sxs-lookup"><span data-stu-id="019a9-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="019a9-119">La parte de la transición de la función se omite si `pTransitionContexts` y `puiTransitionContextCount` ambos son null.</span><span class="sxs-lookup"><span data-stu-id="019a9-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="019a9-120">En este caso, la función proporciona a los llamadores con salida de texto de sólo los nombres de función.</span><span class="sxs-lookup"><span data-stu-id="019a9-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="019a9-121">Si `pTransitionContexts` es null y `puiTransitionContextCount` es no nulo, la función devuelve el número necesario de entradas de contexto en `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="019a9-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="019a9-122">Si `pTransitionContexts` es no nulo, la función lo trata como una matriz de estructuras de longitud `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="019a9-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="019a9-123">El tamaño de la estructura viene dado por `uiSizeOfContext`, y debe ser el tamaño de [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) o `CONTEXT` para la arquitectura.</span><span class="sxs-lookup"><span data-stu-id="019a9-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="019a9-124">`wszTextOut` se escribe en el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="019a9-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="019a9-125">Si el desplazamiento en hexadecimal 0 x 0, no se escribe ningún desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="019a9-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="019a9-126">Si no hay ningún código administrado en el subproceso actualmente en contexto, la función devuelve SOS_E_NOMANAGEDCODE.</span><span class="sxs-lookup"><span data-stu-id="019a9-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="019a9-127">El `Flags` parámetro es 0 o SOS_STACKTRACE_SHOWADDRESSES para ver EBP y ESP delante de cada `module!functionname` línea.</span><span class="sxs-lookup"><span data-stu-id="019a9-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="019a9-128">De forma predeterminada, es 0.</span><span class="sxs-lookup"><span data-stu-id="019a9-128">By default, it is 0.</span></span>  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="019a9-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="019a9-129">Requirements</span></span>  
 <span data-ttu-id="019a9-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="019a9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="019a9-131">**Encabezado**: SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="019a9-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="019a9-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="019a9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="019a9-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="019a9-133">See also</span></span>

- [<span data-ttu-id="019a9-134">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="019a9-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
