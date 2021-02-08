---
description: 'Más información sobre: ICorDebugHeapValue3:: GetMonitorEventWaitList ((método)'
title: ICorDebugHeapValue3::GetMonitorEventWaitList (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
ms.openlocfilehash: ffc849e83151719062133382989344a8f0057caf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791457"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="ed0a9-103">ICorDebugHeapValue3::GetMonitorEventWaitList (Método)</span><span class="sxs-lookup"><span data-stu-id="ed0a9-103">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>

<span data-ttu-id="ed0a9-104">Proporciona una lista ordenada de subprocesos que se ponen en cola en el evento que está asociado a un bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-104">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed0a9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed0a9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed0a9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed0a9-106">Parameters</span></span>  

 `ppThreadEnum`  
 <span data-ttu-id="ed0a9-107">enuncia El enumerador ICorDebugThreadEnum (que proporciona la lista ordenada de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-107">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed0a9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed0a9-108">Return Value</span></span>  

 <span data-ttu-id="ed0a9-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ed0a9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed0a9-110">HRESULT</span></span>|<span data-ttu-id="ed0a9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed0a9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed0a9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed0a9-112">S_OK</span></span>|<span data-ttu-id="ed0a9-113">La lista no está vacía.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-113">The list is not empty.</span></span>|  
|<span data-ttu-id="ed0a9-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ed0a9-114">S_FALSE</span></span>|<span data-ttu-id="ed0a9-115">La lista está vacía.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-115">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ed0a9-116">Excepciones</span><span class="sxs-lookup"><span data-stu-id="ed0a9-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed0a9-117">Notas</span><span class="sxs-lookup"><span data-stu-id="ed0a9-117">Remarks</span></span>  

 <span data-ttu-id="ed0a9-118">El primer subproceso de la lista es el primer subproceso publicado por la siguiente llamada a <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ed0a9-118">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ed0a9-119">El siguiente subproceso de la lista se libera en la llamada siguiente, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-119">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="ed0a9-120">Si la lista no está vacía, este método devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-120">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="ed0a9-121">Si la lista está vacía, el método devuelve S_FALSE; en este caso, la enumeración sigue siendo válida, aunque está vacía.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-121">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="ed0a9-122">En cualquier caso, la interfaz de enumeración solo se puede usar para la duración del estado sincronizado actual.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-122">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="ed0a9-123">Sin embargo, las interfaces del subproceso dispensadas de él son válidas hasta que se cierra el subproceso.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-123">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="ed0a9-124">Si `ppThreadEnum` no es un puntero válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-124">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="ed0a9-125">Si se produce un error de modo que no se pueda determinar qué subprocesos están esperando, si hay alguno, el monitor, el método devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-125">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed0a9-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed0a9-126">Requirements</span></span>  

 <span data-ttu-id="ed0a9-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed0a9-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed0a9-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed0a9-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed0a9-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed0a9-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed0a9-130">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed0a9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0a9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed0a9-131">See also</span></span>

- [<span data-ttu-id="ed0a9-132">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ed0a9-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ed0a9-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="ed0a9-133">Debugging</span></span>](index.md)
