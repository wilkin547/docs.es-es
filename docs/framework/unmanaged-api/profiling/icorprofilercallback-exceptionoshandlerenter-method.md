---
title: "ICorProfilerCallback::ExceptionOSHandlerEnter (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionOSHandlerEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c6ba73ef9551c599c07c4021ff8fff85d53c4a84
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="7ab1a-102">ICorProfilerCallback::ExceptionOSHandlerEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="7ab1a-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="7ab1a-103">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="7ab1a-103">Not implemented.</span></span> <span data-ttu-id="7ab1a-104">Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.</span><span class="sxs-lookup"><span data-stu-id="7ab1a-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab1a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ab1a-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7ab1a-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ab1a-106">Requirements</span></span>  
 <span data-ttu-id="7ab1a-107">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab1a-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab1a-108">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ab1a-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ab1a-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ab1a-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ab1a-110">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab1a-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab1a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ab1a-111">See Also</span></span>  
 [<span data-ttu-id="7ab1a-112">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ab1a-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
