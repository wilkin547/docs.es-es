---
description: 'Más información acerca de: ICorProfilerInfo:: GetInprocInspectionInterface ((método)'
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
ms.openlocfilehash: 5b7ce053f0a64afd5d702a4eb59c1712f4b26e9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781472"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="8a3a8-103">ICorProfilerInfo::GetInprocInspectionInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="8a3a8-103">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>

<span data-ttu-id="8a3a8-104">Obtiene un objeto que se puede consultar para una interfaz "ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="8a3a8-104">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="8a3a8-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="8a3a8-105">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a3a8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a3a8-106">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a3a8-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a3a8-107">Parameters</span></span>  

 `ppicd`  
 <span data-ttu-id="8a3a8-108">objeto [out](/cpp/atl/iunknown) que se puede consultar para una `ICorDebugProcess` interfaz.</span><span class="sxs-lookup"><span data-stu-id="8a3a8-108">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a3a8-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8a3a8-109">Remarks</span></span>  

 <span data-ttu-id="8a3a8-110">La API de depuración de Common Language Runtime (CLR) admite la depuración limitada en proceso en la .NET Framework versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="8a3a8-110">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="8a3a8-111">La depuración en proceso ha habilitado un generador de perfiles para usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="8a3a8-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="8a3a8-112">Como resultado de los comentarios de los clientes, la depuración en proceso se ha quitado del .NET Framework en la versión 2,0 y se ha reemplazado por un conjunto de funcionalidades que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="8a3a8-112">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3a8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a3a8-113">Requirements</span></span>  

 <span data-ttu-id="8a3a8-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a3a8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3a8-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a3a8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a3a8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a3a8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a3a8-117">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="8a3a8-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3a8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a3a8-118">See also</span></span>

- [<span data-ttu-id="8a3a8-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a3a8-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
