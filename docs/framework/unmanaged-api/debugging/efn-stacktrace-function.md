---
description: 'Más información acerca de: _EFN_StackTrace función'
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
ms.openlocfilehash: 6092d0793967cc422e30342783ab4dfd70b33de9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738291"
---
# <a name="_efn_stacktrace-function"></a><span data-ttu-id="b42b3-103">\_EFN \_ StackTrace (función)</span><span class="sxs-lookup"><span data-stu-id="b42b3-103">\_EFN\_StackTrace Function</span></span>

<span data-ttu-id="b42b3-104">Proporciona una representación de texto de un seguimiento de pila administrado y una matriz de registros `CONTEXT`, uno por cada transición entre código no administrado y código administrado.</span><span class="sxs-lookup"><span data-stu-id="b42b3-104">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b42b3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b42b3-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="b42b3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b42b3-106">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="b42b3-107">de Cliente que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="b42b3-107">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="b42b3-108">enuncia Representación de texto del seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="b42b3-108">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="b42b3-109">enuncia Puntero al número de caracteres de `wszTextOut` .</span><span class="sxs-lookup"><span data-stu-id="b42b3-109">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="b42b3-110">enuncia Matriz de contextos de transición.</span><span class="sxs-lookup"><span data-stu-id="b42b3-110">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="b42b3-111">enuncia Puntero al número de contextos de transición de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b42b3-111">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="b42b3-112">de Tamaño de la estructura de contexto.</span><span class="sxs-lookup"><span data-stu-id="b42b3-112">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="b42b3-113">de Establézcalo en 0 o SOS_STACKTRACE_SHOWADDRESSES (0x01) para mostrar el registro EBP y el puntero de pila Enter (ESP) delante de cada `module!functionname` línea.</span><span class="sxs-lookup"><span data-stu-id="b42b3-113">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b42b3-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b42b3-114">Remarks</span></span>  

 <span data-ttu-id="b42b3-115">`_EFN_StackTrace`Se puede llamar a la estructura desde una interfaz de programación WinDbg.</span><span class="sxs-lookup"><span data-stu-id="b42b3-115">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="b42b3-116">Los parámetros se utilizan de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b42b3-116">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="b42b3-117">Si `wszTextOut` es NULL y `puiTextLength` no es null, la función devuelve la longitud de la cadena en `puiTextLength` .</span><span class="sxs-lookup"><span data-stu-id="b42b3-117">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="b42b3-118">Si `wszTextOut` no es null, la función almacena el texto en `wszTextOut` la ubicación indicada por `puiTextLength` .</span><span class="sxs-lookup"><span data-stu-id="b42b3-118">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="b42b3-119">Devuelve un valor correcto si hay suficiente espacio en el búfer o devuelve E_OUTOFMEMORY si el búfer no era suficientemente largo.</span><span class="sxs-lookup"><span data-stu-id="b42b3-119">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="b42b3-120">La parte de la transición de la función se omite si `pTransitionContexts` y `puiTransitionContextCount` son NULL.</span><span class="sxs-lookup"><span data-stu-id="b42b3-120">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="b42b3-121">En este caso, la función proporciona a los llamadores la salida de texto solo de los nombres de función.</span><span class="sxs-lookup"><span data-stu-id="b42b3-121">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="b42b3-122">Si `pTransitionContexts` es NULL y `puiTransitionContextCount` no es null, la función devuelve el número necesario de entradas de contexto en `puiTransitionContextCount` .</span><span class="sxs-lookup"><span data-stu-id="b42b3-122">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="b42b3-123">Si `pTransitionContexts` no es null, la función lo trata como una matriz de estructuras de longitud `puiTransitionContextCount` .</span><span class="sxs-lookup"><span data-stu-id="b42b3-123">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="b42b3-124">Especifica el tamaño de la estructura `uiSizeOfContext` y debe ser el tamaño de [SimpleContext](stacktrace-simplecontext-structure.md) o `CONTEXT` de la arquitectura.</span><span class="sxs-lookup"><span data-stu-id="b42b3-124">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="b42b3-125">`wszTextOut` se escribe en el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="b42b3-125">`wszTextOut` is written in the following format:</span></span>  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="b42b3-126">Si el desplazamiento en Hex es 0X0, no se escribe ningún desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="b42b3-126">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="b42b3-127">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve SOS_E_NOMANAGEDCODE.</span><span class="sxs-lookup"><span data-stu-id="b42b3-127">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="b42b3-128">El `Flags` parámetro es 0 o SOS_STACKTRACE_SHOWADDRESSES para ver EBP y ESP delante de cada `module!functionname` línea.</span><span class="sxs-lookup"><span data-stu-id="b42b3-128">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="b42b3-129">De forma predeterminada, es 0.</span><span class="sxs-lookup"><span data-stu-id="b42b3-129">By default, it is 0.</span></span>  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="b42b3-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b42b3-130">Requirements</span></span>  

 <span data-ttu-id="b42b3-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b42b3-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b42b3-132">**Encabezado:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="b42b3-132">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="b42b3-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b42b3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b42b3-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b42b3-134">See also</span></span>

- [<span data-ttu-id="b42b3-135">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="b42b3-135">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
