---
title: ICorProfilerCallback::ExceptionCLRCatcherFound (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59225677671388b4ed31f7fa440b6e502b604c63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073019"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="45e0c-102">ICorProfilerCallback::ExceptionCLRCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="45e0c-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="45e0c-103">Se le llama cuando un `catch` bloquee durante una excepción se encuentra dentro de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="45e0c-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="45e0c-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="45e0c-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e0c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45e0c-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="45e0c-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45e0c-106">Requirements</span></span>  
 <span data-ttu-id="45e0c-107">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45e0c-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45e0c-108">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45e0c-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45e0c-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45e0c-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45e0c-110">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="45e0c-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e0c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="45e0c-111">See also</span></span>

- [<span data-ttu-id="45e0c-112">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45e0c-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="45e0c-113">Método ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="45e0c-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
