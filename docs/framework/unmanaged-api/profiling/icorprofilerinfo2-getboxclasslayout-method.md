---
title: ICorProfilerInfo2::GetBoxClassLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4dac7e38d1e767a3edeef932a0c0916daffe24b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092037"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="7d5bb-102">ICorProfilerInfo2::GetBoxClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="7d5bb-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="7d5bb-103">Obtiene información sobre dónde se encuentra el tipo de valor especificado al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="7d5bb-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d5bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d5bb-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d5bb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d5bb-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="7d5bb-106">[in] El identificador de la clase que describe el tipo de valor que se aplica.</span><span class="sxs-lookup"><span data-stu-id="7d5bb-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="7d5bb-107">[out] Un entero que es el desplazamiento, en relación con el puntero de identificador de objeto empaquetado del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="7d5bb-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d5bb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d5bb-108">Remarks</span></span>  
 <span data-ttu-id="7d5bb-109">El `pBufferOffset` valor es la ubicación del tipo de valor dentro de un cuadro.</span><span class="sxs-lookup"><span data-stu-id="7d5bb-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="7d5bb-110">Después de `pBufferOffset` se aplica a un objeto sometido a conversión boxing, el diseño de clase del tipo de valor puede usarse para interpretar el valor del objeto.</span><span class="sxs-lookup"><span data-stu-id="7d5bb-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d5bb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d5bb-111">Requirements</span></span>  
 <span data-ttu-id="7d5bb-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d5bb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d5bb-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7d5bb-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d5bb-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d5bb-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7d5bb-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7d5bb-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7d5bb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d5bb-116">See also</span></span>

- [<span data-ttu-id="7d5bb-117">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d5bb-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="7d5bb-118">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d5bb-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
