---
title: ICorProfilerCallback2::ThreadNameChanged (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
ms.openlocfilehash: 8398febd17c7e77f2ad281ebeafc138fca4a47d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718038"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="49dfa-102">ICorProfilerCallback2::ThreadNameChanged (Método)</span><span class="sxs-lookup"><span data-stu-id="49dfa-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>

<span data-ttu-id="49dfa-103">Notifica al generador de perfiles de código que el nombre de un subproceso ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="49dfa-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49dfa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49dfa-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49dfa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="49dfa-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="49dfa-106">de IDENTIFICADOR del subproceso.</span><span class="sxs-lookup"><span data-stu-id="49dfa-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="49dfa-107">de Longitud del nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="49dfa-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="49dfa-108">de Nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="49dfa-108">[in] The new name of the thread.</span></span> <span data-ttu-id="49dfa-109">El nombre no termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="49dfa-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49dfa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49dfa-110">Requirements</span></span>  

 <span data-ttu-id="49dfa-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49dfa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49dfa-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49dfa-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49dfa-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49dfa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49dfa-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49dfa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49dfa-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49dfa-115">See also</span></span>

- [<span data-ttu-id="49dfa-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="49dfa-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="49dfa-117">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="49dfa-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
