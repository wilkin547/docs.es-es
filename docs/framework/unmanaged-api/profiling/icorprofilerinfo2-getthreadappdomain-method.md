---
description: 'Más información acerca de: ICorProfilerInfo2:: GetThreadAppDomain ((método)'
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
ms.openlocfilehash: b480388254a6ee84db9f6c3e8d44b7358246502a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647068"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="d11db-103">ICorProfilerInfo2::GetThreadAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="d11db-103">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>

<span data-ttu-id="d11db-104">Obtiene el identificador del dominio de aplicación en el que el subproceso especificado está ejecutando código actualmente.</span><span class="sxs-lookup"><span data-stu-id="d11db-104">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d11db-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d11db-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d11db-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d11db-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="d11db-107">de IDENTIFICADOR que especifica el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d11db-107">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="d11db-108">enuncia Puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d11db-108">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d11db-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d11db-109">Requirements</span></span>  

 <span data-ttu-id="d11db-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d11db-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d11db-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d11db-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d11db-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d11db-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d11db-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d11db-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11db-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d11db-114">See also</span></span>

- [<span data-ttu-id="d11db-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d11db-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="d11db-116">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d11db-116">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
