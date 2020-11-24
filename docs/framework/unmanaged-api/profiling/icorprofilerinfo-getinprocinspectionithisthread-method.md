---
title: ICorProfilerInfo::GetInprocInspectionIThisThread (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
ms.openlocfilehash: 8daa84e3abbbc64c9a48d8957b4ad9c6756d0d8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682086"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="c8d4f-102">ICorProfilerInfo::GetInprocInspectionIThisThread (Método)</span><span class="sxs-lookup"><span data-stu-id="c8d4f-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>

<span data-ttu-id="c8d4f-103">Obtiene un objeto que se puede consultar para la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="c8d4f-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="c8d4f-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="c8d4f-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d4f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8d4f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8d4f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8d4f-106">Parameters</span></span>  

 `ppicd`  
 <span data-ttu-id="c8d4f-107">objeto [out](/cpp/atl/iunknown) que se puede consultar para la `ICorDebugThread` interfaz.</span><span class="sxs-lookup"><span data-stu-id="c8d4f-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8d4f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c8d4f-108">Remarks</span></span>  

 <span data-ttu-id="c8d4f-109">Los servicios de depuración de Common Language Runtime (CLR) admiten la depuración limitada en proceso en la versión 1,0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8d4f-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="c8d4f-110">La depuración en proceso ha habilitado un generador de perfiles para usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="c8d4f-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="c8d4f-111">Como resultado de los comentarios de los clientes, la depuración en proceso se ha quitado del .NET Framework en la versión 2,0 y se ha reemplazado por un conjunto de funcionalidades que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="c8d4f-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8d4f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8d4f-112">Requirements</span></span>  

 <span data-ttu-id="c8d4f-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8d4f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8d4f-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c8d4f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8d4f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8d4f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8d4f-116">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="c8d4f-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d4f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8d4f-117">See also</span></span>

- [<span data-ttu-id="c8d4f-118">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8d4f-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
