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
ms.openlocfilehash: a543e5119a3ad5580fb67c31dc0e59ab62eab571
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866497"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="7725d-102">ICorProfilerCallback::ExceptionCLRCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="7725d-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="7725d-103">Llamado cuando se encuentra un bloque `catch` para una excepción dentro del propio Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7725d-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="7725d-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="7725d-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7725d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7725d-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="7725d-106">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7725d-106">Requirements</span></span>  
 <span data-ttu-id="7725d-107">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7725d-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7725d-108">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7725d-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7725d-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7725d-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7725d-110">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="7725d-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7725d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7725d-111">See also</span></span>

- [<span data-ttu-id="7725d-112">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7725d-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7725d-113">ExceptionCLRCatcherExecute (método)</span><span class="sxs-lookup"><span data-stu-id="7725d-113">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)
