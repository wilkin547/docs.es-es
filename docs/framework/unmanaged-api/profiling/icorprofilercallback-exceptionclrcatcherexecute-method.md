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
ms.openlocfilehash: b640a6dee9ae50278d6a844d20d21eae156e9dd7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200967"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="0e97d-102">ICorProfilerCallback::ExceptionCLRCatcherExecute (Método)</span><span class="sxs-lookup"><span data-stu-id="0e97d-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="0e97d-103">Se le llama cuando un `catch` bloquear por una excepción que se ejecuta dentro de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0e97d-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="0e97d-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="0e97d-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e97d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e97d-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="0e97d-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e97d-106">Requirements</span></span>  
 <span data-ttu-id="0e97d-107">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e97d-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e97d-108">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e97d-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e97d-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e97d-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e97d-110">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="0e97d-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e97d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e97d-111">See also</span></span>

- [<span data-ttu-id="0e97d-112">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e97d-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0e97d-113">Método ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="0e97d-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
