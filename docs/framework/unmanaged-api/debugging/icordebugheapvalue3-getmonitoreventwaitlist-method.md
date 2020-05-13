---
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
ms.openlocfilehash: 923e9b0821788143fff59eafe10d1802583df7a6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210428"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="91c09-102">ICorDebugHeapValue3::GetMonitorEventWaitList (Método)</span><span class="sxs-lookup"><span data-stu-id="91c09-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>
<span data-ttu-id="91c09-103">Proporciona una lista ordenada de subprocesos que se ponen en cola en el evento que está asociado a un bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="91c09-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91c09-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91c09-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91c09-105">Parameters</span></span>  
 `ppThreadEnum`  
 <span data-ttu-id="91c09-106">enuncia El enumerador ICorDebugThreadEnum (que proporciona la lista ordenada de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="91c09-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91c09-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="91c09-107">Return Value</span></span>  
 <span data-ttu-id="91c09-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="91c09-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="91c09-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91c09-109">HRESULT</span></span>|<span data-ttu-id="91c09-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="91c09-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91c09-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="91c09-111">S_OK</span></span>|<span data-ttu-id="91c09-112">La lista no está vacía.</span><span class="sxs-lookup"><span data-stu-id="91c09-112">The list is not empty.</span></span>|  
|<span data-ttu-id="91c09-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="91c09-113">S_FALSE</span></span>|<span data-ttu-id="91c09-114">La lista está vacía.</span><span class="sxs-lookup"><span data-stu-id="91c09-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="91c09-115">Excepciones</span><span class="sxs-lookup"><span data-stu-id="91c09-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91c09-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91c09-116">Remarks</span></span>  
 <span data-ttu-id="91c09-117">El primer subproceso de la lista es el primer subproceso publicado por la siguiente llamada a <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="91c09-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="91c09-118">El siguiente subproceso de la lista se libera en la llamada siguiente, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="91c09-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="91c09-119">Si la lista no está vacía, este método devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="91c09-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="91c09-120">Si la lista está vacía, el método devuelve S_FALSE; en este caso, la enumeración sigue siendo válida, aunque está vacía.</span><span class="sxs-lookup"><span data-stu-id="91c09-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="91c09-121">En cualquier caso, la interfaz de enumeración solo se puede usar para la duración del estado sincronizado actual.</span><span class="sxs-lookup"><span data-stu-id="91c09-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="91c09-122">Sin embargo, las interfaces del subproceso dispensadas de él son válidas hasta que se cierra el subproceso.</span><span class="sxs-lookup"><span data-stu-id="91c09-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="91c09-123">Si `ppThreadEnum` no es un puntero válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="91c09-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="91c09-124">Si se produce un error de modo que no se pueda determinar qué subprocesos están esperando, si hay alguno, el monitor, el método devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="91c09-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91c09-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91c09-125">Requirements</span></span>  
 <span data-ttu-id="91c09-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91c09-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91c09-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91c09-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91c09-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91c09-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91c09-129">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91c09-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c09-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91c09-130">See also</span></span>

- [<span data-ttu-id="91c09-131">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="91c09-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="91c09-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="91c09-132">Debugging</span></span>](index.md)
