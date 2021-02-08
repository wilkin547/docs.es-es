---
description: 'Más información sobre: método ICorProfilerCallback2:: Threadnamechanged ('
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
ms.openlocfilehash: 161247f9692d1307d063e244b200eb0d8f739e9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799049"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="88653-103">ICorProfilerCallback2::ThreadNameChanged (Método)</span><span class="sxs-lookup"><span data-stu-id="88653-103">ICorProfilerCallback2::ThreadNameChanged Method</span></span>

<span data-ttu-id="88653-104">Notifica al generador de perfiles de código que el nombre de un subproceso ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="88653-104">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88653-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88653-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88653-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88653-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="88653-107">de IDENTIFICADOR del subproceso.</span><span class="sxs-lookup"><span data-stu-id="88653-107">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="88653-108">de Longitud del nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="88653-108">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="88653-109">de Nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="88653-109">[in] The new name of the thread.</span></span> <span data-ttu-id="88653-110">El nombre no termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="88653-110">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88653-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88653-111">Requirements</span></span>  

 <span data-ttu-id="88653-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88653-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88653-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="88653-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="88653-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88653-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88653-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88653-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88653-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="88653-116">See also</span></span>

- [<span data-ttu-id="88653-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88653-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="88653-118">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88653-118">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
