---
title: ICorProfilerInfo::GetInprocInspectionInterface (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
ms.openlocfilehash: 2fe0b314f761cf3c7a3a926d40c69302d0ece000
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498094"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="36289-102">ICorProfilerInfo::GetInprocInspectionInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="36289-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="36289-103">Obtiene un objeto que se puede consultar para una interfaz "ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="36289-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="36289-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="36289-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36289-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36289-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36289-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36289-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="36289-107">objeto [out](/cpp/atl/iunknown) que se puede consultar para una `ICorDebugProcess` interfaz.</span><span class="sxs-lookup"><span data-stu-id="36289-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36289-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36289-108">Remarks</span></span>  
 <span data-ttu-id="36289-109">La API de depuración de Common Language Runtime (CLR) admite la depuración limitada en proceso en la .NET Framework versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="36289-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="36289-110">La depuración en proceso ha habilitado un generador de perfiles para usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="36289-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="36289-111">Como resultado de los comentarios de los clientes, la depuración en proceso se ha quitado del .NET Framework en la versión 2,0 y se ha reemplazado por un conjunto de funcionalidades que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="36289-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36289-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36289-112">Requirements</span></span>  
 <span data-ttu-id="36289-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36289-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36289-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36289-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36289-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36289-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36289-116">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="36289-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36289-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="36289-117">See also</span></span>

- [<span data-ttu-id="36289-118">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36289-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
