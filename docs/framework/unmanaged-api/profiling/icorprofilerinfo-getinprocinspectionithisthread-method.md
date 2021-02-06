---
description: 'Más información acerca de: ICorProfilerInfo:: Getinprocinspectionithisthread ((método)'
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
ms.openlocfilehash: 07ff904170750976e54e623101a2552db0c7f290
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647250"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="acea9-103">ICorProfilerInfo::GetInprocInspectionIThisThread (Método)</span><span class="sxs-lookup"><span data-stu-id="acea9-103">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>

<span data-ttu-id="acea9-104">Obtiene un objeto que se puede consultar para la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="acea9-104">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="acea9-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="acea9-105">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acea9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acea9-106">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acea9-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="acea9-107">Parameters</span></span>  

 `ppicd`  
 <span data-ttu-id="acea9-108">objeto [out](/cpp/atl/iunknown) que se puede consultar para la `ICorDebugThread` interfaz.</span><span class="sxs-lookup"><span data-stu-id="acea9-108">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acea9-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="acea9-109">Remarks</span></span>  

 <span data-ttu-id="acea9-110">Los servicios de depuración de Common Language Runtime (CLR) admiten la depuración limitada en proceso en la versión 1,0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="acea9-110">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="acea9-111">La depuración en proceso ha habilitado un generador de perfiles para usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="acea9-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="acea9-112">Como resultado de los comentarios de los clientes, la depuración en proceso se ha quitado del .NET Framework en la versión 2,0 y se ha reemplazado por un conjunto de funcionalidades que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="acea9-112">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acea9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acea9-113">Requirements</span></span>  

 <span data-ttu-id="acea9-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acea9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acea9-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="acea9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="acea9-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acea9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acea9-117">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="acea9-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acea9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="acea9-118">See also</span></span>

- [<span data-ttu-id="acea9-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="acea9-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
