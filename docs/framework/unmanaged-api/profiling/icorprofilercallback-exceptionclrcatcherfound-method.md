---
description: 'Más información sobre: ICorProfilerCallback:: Exceptionclrcatcherfound ((método)'
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
ms.openlocfilehash: 37027a00e488eed5681b1d99ada6332d59e6a632
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706310"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="67210-103">ICorProfilerCallback::ExceptionCLRCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="67210-103">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>

<span data-ttu-id="67210-104">Llamado cuando `catch` se encuentra un bloque para una excepción dentro del propio Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="67210-104">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="67210-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="67210-105">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67210-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67210-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="67210-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67210-107">Requirements</span></span>  

 <span data-ttu-id="67210-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67210-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67210-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67210-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67210-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67210-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67210-111">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="67210-111">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67210-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="67210-112">See also</span></span>

- [<span data-ttu-id="67210-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="67210-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="67210-114">Método ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="67210-114">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)
