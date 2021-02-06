---
description: 'Más información sobre: ICorProfilerCallback:: Exceptionclrcatcherexecute ((método)'
title: ICorProfilerCallback::ExceptionCLRCatcherExecute (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: cb6926fdfcc9b5ffef20cc69c71a3bafefd9f6ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657507"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="4b54b-103">ICorProfilerCallback::ExceptionCLRCatcherExecute (Método)</span><span class="sxs-lookup"><span data-stu-id="4b54b-103">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>

<span data-ttu-id="4b54b-104">Se llama cuando `catch` se ejecuta un bloque para una excepción dentro del propio Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4b54b-104">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="4b54b-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="4b54b-105">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b54b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b54b-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="4b54b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b54b-107">Requirements</span></span>  

 <span data-ttu-id="4b54b-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b54b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b54b-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b54b-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b54b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b54b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b54b-111">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="4b54b-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b54b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b54b-112">See also</span></span>

- [<span data-ttu-id="4b54b-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b54b-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4b54b-114">Método ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="4b54b-114">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
