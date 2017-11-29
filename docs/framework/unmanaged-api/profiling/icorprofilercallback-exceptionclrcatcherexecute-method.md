---
title: "ICorProfilerCallback::ExceptionCLRCatcherExecute (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b63f428cd75ed98d30e4b6ecca69dbe3b5b5656d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="58fbd-102">ICorProfilerCallback::ExceptionCLRCatcherExecute (Método)</span><span class="sxs-lookup"><span data-stu-id="58fbd-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="58fbd-103">Llamado cuando un `catch` bloquee durante una excepción se ejecuta dentro de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="58fbd-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="58fbd-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58fbd-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58fbd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58fbd-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="58fbd-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58fbd-106">Requirements</span></span>  
 <span data-ttu-id="58fbd-107">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58fbd-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58fbd-108">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58fbd-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58fbd-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58fbd-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58fbd-110">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="58fbd-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58fbd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="58fbd-111">See Also</span></span>  
 [<span data-ttu-id="58fbd-112">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58fbd-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="58fbd-113">ExceptionCLRCatcherFound (método)</span><span class="sxs-lookup"><span data-stu-id="58fbd-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
