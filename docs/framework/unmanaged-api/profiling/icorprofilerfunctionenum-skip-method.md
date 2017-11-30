---
title: "ICorProfilerFunctionEnum::Skip (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Skip Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c5142b091ec32c162daaca9c53cb65763bb5ed7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="2ec77-102">ICorProfilerFunctionEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="2ec77-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="2ec77-103">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="2ec77-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ec77-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ec77-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ec77-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2ec77-106">[in] El número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="2ec77-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ec77-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2ec77-107">Return Value</span></span>  
 <span data-ttu-id="2ec77-108">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2ec77-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2ec77-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ec77-109">HRESULT</span></span>|<span data-ttu-id="2ec77-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ec77-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ec77-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ec77-111">S_OK</span></span>|<span data-ttu-id="2ec77-112">`celt`elementos omitidos.</span><span class="sxs-lookup"><span data-stu-id="2ec77-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="2ec77-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2ec77-113">S_FALSE</span></span>|<span data-ttu-id="2ec77-114">Menos de `celt` elementos omitidos, lo que indica que no hay ningún elemento más.</span><span class="sxs-lookup"><span data-stu-id="2ec77-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ec77-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ec77-115">Remarks</span></span>  
 <span data-ttu-id="2ec77-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="2ec77-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ec77-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ec77-117">Requirements</span></span>  
 <span data-ttu-id="2ec77-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ec77-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ec77-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2ec77-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2ec77-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ec77-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ec77-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ec77-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec77-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ec77-122">See Also</span></span>  
 [<span data-ttu-id="2ec77-123">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ec77-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="2ec77-124">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2ec77-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
