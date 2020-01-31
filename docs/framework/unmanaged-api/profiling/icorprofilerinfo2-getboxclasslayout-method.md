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
ms.openlocfilehash: 500cf74c320438fc1b78f0aac737b418716e1a11
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862847"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="e8ab2-102">ICorProfilerInfo2::GetBoxClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="e8ab2-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="e8ab2-103">Obtiene información sobre dónde se encuentra el tipo de valor especificado cuando se le aplica la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="e8ab2-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ab2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8ab2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8ab2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="e8ab2-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="e8ab2-106">de IDENTIFICADOR de la clase que describe el tipo de valor al que se aplica la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="e8ab2-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="e8ab2-107">enuncia Entero que es el desplazamiento con respecto al puntero de identificador de objeto con conversión boxing del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="e8ab2-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8ab2-108">Notas</span><span class="sxs-lookup"><span data-stu-id="e8ab2-108">Remarks</span></span>  
 <span data-ttu-id="e8ab2-109">El valor `pBufferOffset` es la ubicación del tipo de valor dentro de un cuadro.</span><span class="sxs-lookup"><span data-stu-id="e8ab2-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="e8ab2-110">Una vez que se aplica `pBufferOffset` a un objeto con conversión boxing, el diseño de clase del tipo de valor se puede utilizar para interpretar el valor del objeto.</span><span class="sxs-lookup"><span data-stu-id="e8ab2-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8ab2-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e8ab2-111">Requirements</span></span>  
 <span data-ttu-id="e8ab2-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8ab2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8ab2-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8ab2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8ab2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8ab2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8ab2-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8ab2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ab2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8ab2-116">See also</span></span>

- [<span data-ttu-id="e8ab2-117">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8ab2-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="e8ab2-118">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8ab2-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
