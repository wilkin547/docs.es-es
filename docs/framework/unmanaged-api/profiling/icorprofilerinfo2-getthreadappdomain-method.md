---
title: ICorProfilerInfo2::GetThreadAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
ms.openlocfilehash: 7c1ee1c39fbf2dcc1f16df3bc94a235676a216dd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862573"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="1348f-102">ICorProfilerInfo2::GetThreadAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="1348f-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="1348f-103">Obtiene el identificador del dominio de aplicación en el que el subproceso especificado está ejecutando código actualmente.</span><span class="sxs-lookup"><span data-stu-id="1348f-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1348f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1348f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1348f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1348f-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="1348f-106">de IDENTIFICADOR que especifica el subproceso.</span><span class="sxs-lookup"><span data-stu-id="1348f-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="1348f-107">enuncia Puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1348f-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1348f-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1348f-108">Requirements</span></span>  
 <span data-ttu-id="1348f-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1348f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1348f-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1348f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1348f-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1348f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1348f-112">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1348f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1348f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1348f-113">See also</span></span>

- [<span data-ttu-id="1348f-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1348f-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="1348f-115">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1348f-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
