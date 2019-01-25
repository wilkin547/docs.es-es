---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e92ca55a04032ad9950888eb59e33ee815b14d42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514622"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="b8642-102">ICorProfilerCallback::ExceptionCLRCatcherExecute (Método)</span><span class="sxs-lookup"><span data-stu-id="b8642-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="b8642-103">Se le llama cuando un `catch` bloquear por una excepción que se ejecuta dentro de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b8642-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="b8642-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="b8642-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8642-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8642-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="b8642-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8642-106">Requirements</span></span>  
 <span data-ttu-id="b8642-107">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8642-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8642-108">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8642-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8642-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8642-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8642-110">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="b8642-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8642-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8642-111">See also</span></span>
- [<span data-ttu-id="b8642-112">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8642-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b8642-113">ExceptionCLRCatcherFound (método)</span><span class="sxs-lookup"><span data-stu-id="b8642-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
